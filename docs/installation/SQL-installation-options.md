# SQL installation options
Access Manager requires a Microsoft SQL Server 2017 or higher database. The setup program can install a pre-configured instance of SQL express, or you can choose to use an existing SQL server, or even an Azure SQL database.

## Using the pre-configured SQL Express instance
During installation, you can choose to have a pre-configured instance of SQL Express installed. The installer will create and configure a new SQL express instance (named `AMS`) on the local machine. Access to the database will be restricted to local administrators and the AMS service account.

This is suitable for small to medium sized installations of Access Manager, and has a number of benefits such as being completely configured and managed by the AMS service itself.
Do note that SQL express has several limitations that you will need to consider;
- 1GB maximum memory used by the database engine
- 10GB maximum database size
- 1MB maximum buffer cache
- Limited to the lesser of one (1) CPU socket or four (4) cores 

For larger installations of Access Manager, you should consider using SQL server Standard or Enterprise edition.

If you are using the high-availability feature of Access Manager to run in a failover cluster, you cannot use SQL Express. We recommend installing a clustered instance of SQL server side-by-side in the same cluster as Access Manager. Alternatively, use a Azure SQL database configured for high availability.

## Using SQL Standard or Enterprise Edition
If you are running Access Manager in a large environment, or SQL express is otherwise not suitable, you can set up the AMS database on an SQL instance of your choosing. You must manually set up your instance, and create the database, before running the installer. During installation, you will be prompted for the server and instance name. 

The database should be called `AccessManager` and the AMS service account must be added to the `db_owner` role of the database. Your database administrator can do this for you, or you can use the script below to create a new database with the default settings, and assign the correct permissions.

### Installation steps 
Use the following steps to manually create the database, allowing you to specify advanced properties like where the database files will be located, how big they should be initially and how much they should grow by, and what recovery mode to use. 

1. Create a new database on the SQL server with the name `AccessManager`. 
2. Create a login for the service account
3. Map the service account login to the `AccessManager` database
4. Add the service account to the `db_owner` role for the `AccessManager` database
5. Once these steps are complete, you can run the AMS installer, and specify your SQL server name and instance when prompted

Alternatively, you can use the following script to create a basic database with default settings. Note, that the default settings may not result in a database that is suitable for production use. You should ensure that at least the following settings are appropriate for your environment
1. Database file location
2. Database initial size and auto growth settings
3. Ensure the recovery mode matches your backup strategy and recovery point objectives

```sql
/*
---------------------------------------------------------------
Access Manager SQL database build script
	Step 1. Modify the @ServiceAccount variable to contain the account name of the service account that is used to run the AMS service
                If the service account is a group-manged service account, don't forget to add the '$' character to the end of the account name
	Step 2. Run this script to set the appropriate permissions on the database
---------------------------------------------------------------
*/
DECLARE @ServiceAccount nvarchar(256) = 'DOMAIN\svc-lithnetams$'

---- Do not modify
DECLARE @ServiceAccountQuoted nvarchar(256) = QUOTENAME(@ServiceAccount);

IF DB_ID('AccessManager') IS NULL 
BEGIN
    -- Get the SQL Server data path.
        DECLARE @data_path nvarchar(256);       
        SET @data_path = (SELECT SUBSTRING(physical_name, 1, CHARINDEX(N'master.mdf', LOWER(physical_name)) - 1)
                FROM master.sys.master_files
                WHERE database_id = 1 AND file_id = 1);

	  EXECUTE ('
CREATE DATABASE [AccessManager]
 CONTAINMENT = NONE
 ON  PRIMARY 
( NAME = N''AccessManager'', FILENAME = "' + @data_path + 'AccessManager.mdf", SIZE = 1048576KB , FILEGROWTH = 131072KB )
 LOG ON 
( NAME = N''AccessManager_log'', FILENAME = "' + @data_path + 'AccessManager.ldf", SIZE = 524288KB , FILEGROWTH = 65536KB )

')
    
    ALTER DATABASE [AccessManager] SET RECOVERY SIMPLE 
    PRINT 'Created database'
END

IF NOT EXISTS 
    (SELECT name  
     FROM [master].sys.server_principals
     WHERE name = @ServiceAccount )
BEGIN
      EXEC ('CREATE LOGIN ' + @ServiceAccountQuoted + ' FROM WINDOWS WITH DEFAULT_DATABASE=[AccessManager]');
	  PRINT 'Created server login'
END

IF NOT EXISTS
    (SELECT (1)
        FROM [master].sys.server_principals sp
        JOIN [AccessManager].sys.database_principals dp on dp.sid = sp.sid
        WHERE sp.name = @ServiceAccount )
BEGIN
    EXEC ('USE [AccessManager]; CREATE USER ' + @ServiceAccountQuoted + ' FOR LOGIN ' + @ServiceAccountQuoted);
	PRINT 'Mapped service account login to database user'
END

DECLARE @name nvarchar(250) = (SELECT dp.name FROM [master].sys.server_principals sp
        JOIN [AccessManager].sys.database_principals dp on dp.sid = sp.sid
        WHERE sp.name = @ServiceAccount)

IF (@name <> 'dbo')
BEGIN
    EXEC ('USE [AccessManager]; ALTER ROLE [db_owner] ADD MEMBER ' + @ServiceAccountQuoted)
	PRINT 'Granted db_owner role to service account'
END

```

## Using Azure SQL
Using an Azure SQL database is fully supported by Access Manager. You'll need to create an empty database before running the installer, and create a login for the AMS service to use.

### Installation steps 
1. From the Azure Portal, create a new `SQL Database` resource
2. Follow the wizard prompts, specifying the database name, and instance type as appropriate. We recommend you use the name `AccessManager`
3. Once the database has been provisioned, open the new resource
4. Select the `Query editor` option from the left menu, and authenticate to the instance
5. In the query editor window, paste the following code after modifying the password field to contain your own strong password

```sql
CREATE USER [svc-lithnetams] WITH password='your-password-here';
EXEC sp_addrolemember 'db_owner', 'svc-lithnetams';

```

6. Run the code to create a user in the database for the service account to use
7. From the menu on the left-hand side, select `Connection Strings`, and copy the `ADO.NET` connection string
8. Modify the username and password in the connection string to contain the username and password you created earlier. Your connection string should look similar to below

```
Server=tcp:ams.database.windows.net,1433;Initial Catalog=AccessManager;Persist Security Info=False;User ID=svc-lithnetams;Password=your-password-here;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;
```
9. Once these steps are complete, you can run the AMS installer, and provide the connection string when prompted.

## Using Amazon RDS
Using a AWS RDS Microsoft SQL database is fully supported by Access Manager. You'll need to create an empty database before running the installer, and create a login for the AMS service to use.

### Installation steps 
1. From the AWS Console, create a new `Microsoft SQL Server` RDS resource
2. Select the appropriate options and instance configuration for your environment
3. Once the server has been provisioned, ensure you allow the AMS server access to the RDS instance via the appropriate security groups
4. Using Microsoft SQL Management Studio, connect to the RDS instance using the admin credentials created during the setup process
5. In the query editor window, paste the following code after modifying the password field to contain your own strong password

```sql

CREATE LOGIN [svc-lithnetams] WITH password='your-password-here';
GO

-- Get the SQL Server data path.
DECLARE @data_path nvarchar(256);       
SET @data_path = (SELECT SUBSTRING(physical_name, 1, CHARINDEX(N'master.mdf', LOWER(physical_name)) - 1)
        FROM master.sys.master_files
        WHERE database_id = 1 AND file_id = 1);

EXECUTE ('
CREATE DATABASE [AccessManager]
 CONTAINMENT = NONE
 ON  PRIMARY 
( NAME = N''AccessManager'', FILENAME = "' + @data_path + 'AccessManager.mdf", SIZE = 1048576KB , FILEGROWTH = 131072KB )
 LOG ON 
( NAME = N''AccessManager_log'', FILENAME = "' + @data_path + 'AccessManager.ldf", SIZE = 524288KB , FILEGROWTH = 65536KB )
')

USE [AccessManager]

CREATE USER [svc-lithnetams] FOR LOGIN [svc-lithnetams]
EXEC sp_addrolemember 'db_owner', 'svc-lithnetams';
```
6. Modify the username and password in the connection string below to contain the username and password you created in the step above. Your connection string should look similar to below

```
Server=tcp:ams.database.windows.net,1433;Initial Catalog=AccessManager;Persist Security Info=False;User ID=svc-lithnetams;Password=your-password-here;MultipleActiveResultSets=False;Connection Timeout=30;
```
9. Once these steps are complete, you can run the AMS installer, and provide the connection string when prompted.

## Security considerations
It is important to secure access to your database. It contains information used by computers to authenticate to the AMS directory, as well as their group membership. 

We recommend that if possible, the database server is kept dedicated for Access Manager, and not shared with other applications. Administrators of the database server should be restricted to AMS admins only. 
