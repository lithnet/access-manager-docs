## SQL installation
Access Manager requires a Microsoft SQL Server 2017 or higher database. The setup program can install a pre-configured instance of SQL express, or you can use an SQL server your have set up previously. 

## Using the pre-configured SQL Express instance
During installation, you can choose to have a pre-configured instance of SQL Express installed. The installer will create and configure a new SQL express instance (named `AMS`) on the local machine. Access to the database will be restricted to local administrators, the nominated AMS administrators group, and the AMS service account.

This is suitable for smaller installations of Access Manager, noting that SQL express has several limitations;

- 1GB maximum memory used by the database engine
- 10GB maximum database size
- 1MB maximum buffer cache
- Limited to the lesser of one (1) CPU socket or four (4) cores 

For larger installations of Access Manager, you should consider using SQL server Standard or Enterprise edition.

If you are using the high-availability feature of Access Manager to run in a failover cluster, you cannot use SQL Express.

## Using SQL Standard or Enterprise Edition
If you are running Access Manager in a large environment, or SQL express is otherwise  not suitable, you can set up the AMS database on an SQL instance of your choosing. You must manually setup your instance, and create the database, before running the installer. During installation, you will be prompted for the server and instance name.

### Security considerations
It is important to secure access to your database. It contains information used by computers to authenticate to the AMS directory, as well as their group membership. Encrypted passwords are also stored in the database, however, the encryption key needed to decrypt them is stored only on the AMS server.

We recommend that if possible, the database server is kept dedicated for Access Manager, and not shared with other applications. Administrators of the database server should be restricted to AMS admins only. In simplified deployments, you can install the SQL software on the AMS server itself.

### Installation steps
1. Create a new database on the SQL server with the name `AccessManager`
2. Run the following script, modifying the variables as instructed
3. Once these steps are complete, you can run the AMS installer, and specify your SQL server name and instance when prompted

```sql
/*
---------------------------------------------------------------
Access Manager SQL database build script

	Step 1. Create a new database called 'AccessManager'
	Step 2. Modify the @ServiceAccount variable to contain the account name of the service account that is used to run the AMS service
	Step 3. Modify the @AmsAdminsGroup variable to contain the name of the group that contains all the AMS administrators
	Step 4. Run this script to set the appropriate permissions on the database

---------------------------------------------------------------
*/

DECLARE @ServiceAccount nvarchar(256) = 'DOMAIN\svc-lithnetams'
DECLARE @AmsAdminsGroup nvarchar(256) = 'DOMAIN\AmsAdmins'

---- Do not modify
DECLARE @ServiceAccountQuoted nvarchar(256) = QUOTENAME(@ServiceAccount);
DECLARE @AmsAdminsGroupQuoted nvarchar(256) = QUOTENAME(@AmsAdminsGroup);

IF @ServiceAccount NOT IN (SELECT name FROM sys.server_principals)
        EXEC ('CREATE LOGIN ' + @ServiceAccountQuoted + ' FROM WINDOWS WITH DEFAULT_DATABASE=[AccessManager]');
IF @AmsAdminsGroup NOT IN (SELECT name FROM sys.server_principals)
        EXEC ('CREATE LOGIN ' + @AmsAdminsGroupQuoted + ' FROM WINDOWS');

USE [AccessManager]
IF @ServiceAccount NOT IN (SELECT name FROM sys.database_principals)
        EXEC ('USE [AccessManager]; CREATE USER ' + @ServiceAccountQuoted + ' FOR LOGIN ' + @ServiceAccountQuoted);
IF @AmsAdminsGroup NOT IN (SELECT name FROM sys.database_principals)
        EXEC ('USE [AccessManager]; CREATE USER ' + @AmsAdminsGroupQuoted + ' FOR LOGIN ' + @AmsAdminsGroupQuoted);
			   
 EXEC ('ALTER ROLE [db_owner] ADD MEMBER ' + @ServiceAccountQuoted);
 EXEC ('ALTER ROLE [db_owner] ADD MEMBER ' + @AmsAdminsGroupQuoted);

```