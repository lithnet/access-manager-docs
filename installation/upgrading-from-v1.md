# Upgrading from Access Manager v1 to v3

## Summary

There are several methods you can use to upgrade AMS to version 2, and a few things you will need to plan for.

- Access Manager v3 requires an SQL server. You can either use the built-in Microsoft SQL Express instance, or an external SQL server. [You'll need to plan for where you will set your database up](installing-the-access-manager-server/sql-installation-options.md), and ensure you have an appropriate database backup strategy in place.
- If you had deployed AMS in a failover cluster, the shared storage is no longer a requirement, but can remain if you'd like to have a central copy of the log files.

## Upgrading the Access Manager Agent

If you've deployed the Access Manger *Agent* in your environment, you can simply deploy the new version. There are no changes in functionality or behavior from v1.0 for domain-joined hosts. 

## Upgrade the Access Manager Server 
### Method 1: In-place upgrade
The in-place upgrade process from Access Manager v1 to v3 is very straight forward. You simply install the new version of AMS over the top, and the application will take care of importing the configuration from v1 automatically. 

We recommend taking a backup of the server, or at least the `config` folder, before you begin the upgrade process.

A few notes about this method
- Access Manager v3 no longer uses the `appsettings.json` file to store its configuration. Upon installation, the configuration will be imported into the database, and the file renamed `appsettings.json.<date>.backup`
- All authorization rules, audit templates, scripts, certificates and user interface configuration will be imported into the database. Scripts and template files remain on the disk in the `config` folder, but are no longer used.

### Upgrade method 2: Deploying to a new server and importing existing configuration
If you do not wish to upgrade your existing server, and want to deploy v3 on a new server, while keeping all your configuration then follow these steps.

#### From the AMS v1 server
1. From the AMS v1 server, navigate to the `config` folder that was specified during installation. This is usually `C:\Program Files\Lithnet\Access Manager Service\config`, unless modified at installation time.
2. From the config folder, copy all files and folders _except_ for the `db` folder. The database does not contain stateful information, and does not need to be migrated to v3.
3. Open the configuration tool, navigate to the `Local admin passwords` tab, and export any encryption certificates that are present.

#### On the new server
> Migration of config to a new server must be done before the new server is configured. If configuration has taken place on the new server, then an import of settings is not possible. You will still be able to import authorization rules, as per the section on Upgrade method 3.

1. Install the Access Manager v3 service onto the new host. Do not open the configuration tool when prompted by the installer. If you configure the new instance, a configuration import is not possible.
2. Stop the `Lithnet Access Manager Service` Windows service
3. Copy the contents of the `config` folder obtained for the v1 installation, and place it in the v3 server's `config` folder.
4. The config folder should now contain the `appsettings.json` file, the `scripts` folder, and the `templates` folder.
5. Start the `Lithnet Access Manager Service` Windows service
6. Open the `access-manager-v1-migration.log` file located by default in the `logs` folder at `C:\Program Files\Lithnet\Access Manager Service\logs` and check for any migration errors
>  Note that encrypted values such as the OpenID Connect application secret, and SMTP password cannot be migrated from one server to another, and will be set to blank values. You will need to reset these from the configuration tool to the correct value.
7. Open the configuration tool, and navigate to the `Directory Configuration`, `Active Directory`, `Lithnet LAPS` page. If you exported encryption certificates from the v1 instance, re-import those certificates here.
8. Enter any OpenID Connect or SMTP passwords that were not migrated from the import process.
9. Validate the configuration is as you expect, and then save the settings.

### Upgrade method 3: Importing authorization rules
The final upgrade method is to deploy a new server, install Access Manager, and configure it from scratch, but then importing only the authorization rules and associated notification channels from the v1 server.

1. On the AMS v1 host, navigate to the applications `config` folder using Windows Explorer. (By default this is at `C:\Program Files\Lithnet\Access Manager Server\config`). From there, copy the `appsettings.json`, as well as the `audit-templates` and `scripts` folders.
2. Copy these files to the new host, and place them in a new folder, keeping the original structure intact (e.g. `appsettings.json` file is in the same folder as the `audit-templates` and `scripts` folders).
3. Install Access Manager v3 onto the new host.
4. Open the configuration tool and configure the app according to the [setup guide](installing-the-access-manager-server/installing-the-access-manager-service.md)
5. Navigate to `Authorization Rules`, `Computer`, and click the `Import authorization rules` button.
6. When prompted, select the option to `Import authorization rules from an Access Manager v1.0 config folder`
7. Select the path to folder you created that contains the `appsettings.json` file and associated sub folders. Optionally select if the import wizard should also import your notification channels and subscriptions for each rule.
8. Validate the rule settings, and make any modifications that are appropriate, and import them into your v3 system when you are ready.
9. Save your configuration to commit the new rules to the server.

## Changed functionality

### Just-in-time Access changes
In Access Manager v1, when the JIT feature was used in an Active Directory domain that did not have the privilege access management optional feature turned enabled, AMS would fall back to a mechanism that used [Active Directory dynamic objects](https://docs.microsoft.com/en-us/windows/win32/ad/dynamic-objects). These are objects that self-delete after a period of time. While this served the JIT function well, each JIT request consumed a RID from the [RID pool](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/manage/managing-rid-issuance) - a large, but finite resource.

In order to better manage Active Directory resources, AMS v3 has moved to an internal scheduler to manage the removal of principals from groups when their access period has expired.

There are no configuration changes required to AMS or AD to transition to the internal scheduler. However, it is important to note, that if the AMS server is offline at the time when a user's JIT access was scheduled to be removed, the removal will not take place. However, when the AMS server is brought back online, the scheduled removals will take place immediately.

Enterprise edition customers can run multiple front-end AMS servers. As long as one of the servers is up, then the scheduled removal will be executed.

The gold standard for JIT access, will always be using the [Privileged Access Management optional forest feature](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-adts/d079eee8-1bac-4b03-86e4-506a21450905) of Active Directory. We do recommend upgrading to Windows Server 2016 functional level, and enabling the PAM optional feature for the best JIT experience possible. Access Manager will always use this mode for JIT if it is available in the domain.

### Audit templates
Access Manager v1 allowed you to provide an individual success and failure file to be used for email and webhook templates.

Access Manager v3 introduces a powerful new rendering engine that allows you to have a single template file, and conditionally render it based on the audit data to your choosing. This is done using the [handlebars](https://handlebarsjs.com/) language. 

The import process will automatically convert your success and failure templates into a new conditionally rendered file. Audit events will appear and behave just as they did in v1.

However, if you plan to use JIT for roles, you'll need to [create new templates](../help-and-support/advanced-help-topics/audit-templates.md) that accommodate role auditing alongside computer auditing. You can use the imported scripts, but they may not contain all the information you expect. Simply create a new email or webhook audit channel, and the new format templates will be pre-filled for you.

### Audit scripts
Changes were also made to the PowerShell audit scripts feature. All your existing scripts will be imported, and will work for computer authorization auditing, as they do today. They will be marked as v1 scripts in the UI.

In order to process JIT for roles events, you'll need to update them to the [new v3 script format](../help-and-support/advanced-help-topics/audit-scripts.md).

Note that support for v1 audit scripts will be removed in a future version of Access Manager.

### Certificate authentication
In line with the certificate-based authentication changes announced by Microsoft in [KB5014754](https://support.microsoft.com/en-us/topic/kb5014754-certificate-based-authentication-changes-on-windows-domain-controllers-ad2c23b0-15d8-4340-a468-4d4f3b188f16), Access Manager v3, by default, now only accepts certificates containing the user's SID in an extension with OID `1.3.6.1.4.1.311.25.2`.

If your certificates were issued before this patch was installed, they will not contain this new extension, and AMS will fail to authenticate the user. In order to resolve this issue, you can enable the old behavior from the [Authentication](../configuration/setting-up-authentication/setting-up-smart-card-authentication.md) page, by selecting `Enable weak identity bindings` and select `enable UPN mapping`.