# Upgrading from Access Manager v1 to v2

## Summary

The upgrade process from Access Manager v1 to v2 is very straight forward. You simply install the new version of AMS over the top, and the application will take care of importing the configuration from v1 automatically. 

We recommend taking a backup of the server, or at least the `config` folder, before you begin the upgrade process.

There are a few things to note about v2 that you will need to plan for;

- Access Manager v2 requires an SQL server, [you'll need to plan for where you will set your database up](installing-the-access-manager-server/sql-installation-options.md), and ensure you have an appropriate database backup strategy in place.
- Access Manager v2 no longer uses the `appsettings.json` file to store its configuration. Upon installation, the configuration will be imported into the database, and the file renamed `appsettings.json.<date>.backup`
- All authorization rules, audit templates, scripts, certificates and user interface configuration will be imported into the database. Scripts and template files remain on the disk in the `config` folder, but are no longer used.
- If you had deployed AMS in a failover cluster, the shared storage is no longer a requirement, but can remain if you'd like to have a central copy of the log files.

If you've deployed the Access Manger Agent in your environment, you can simply deploy the new version. There are no changes in functionality or behavior from v1.0

## Changed functionality

### Just-in-time Access changes
In Access Manager v1, when the JIT feature was used in an Active Directory domain that did not have the privilege access management optional feature turned enabled, AMS would fall back to a mechanism that used [Active Directory dynamic objects](https://docs.microsoft.com/en-us/windows/win32/ad/dynamic-objects). These are objects that self-delete after a period of time. While this served the JIT function well, each JIT request consumed a RID from the [RID pool](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/manage/managing-rid-issuance) - a large, but finite resource.

In order to better manage Active Directory resources, AMS v2 has moved to an internal scheduler to manage the removal of principals from groups when their access period has expired.

There are no configuration changes required to AMS or AD to transition to the internal scheduler. However, it is important to note, that if the AMS server is offline at the time when a user's JIT access was scheduled to be removed, the removal will not take place. However, when the AMS server is brought back online, the scheduled removals will take place immediately.

Enterprise edition customers can run multiple front-end AMS servers. As long as one of the servers is up, then the scheduled removal will be executed.

The gold standard for JIT access, will always be using the [Privileged Access Management optional forest feature](https://docs.microsoft.com/en-us/openspecs/windows\_protocols/ms-adts/d079eee8-1bac-4b03-86e4-506a21450905) of Active Directory. We do recommend upgrading to Windows Server 2016 functional level, and enabling the PAM optional feature for the best JIT experience possible. Access Manager will always use this mode for JIT if it is available in the domain.

### Audit templates
Access Manager v1 allowed you to provide an individual success and failure file to be used for email and webhook templates.

Access Manager v2 introduces a powerful new rendering engine that allows you to have a single template file, and conditionally render it based on the audit data to your choosing. This is done using the [handlebars](https://handlebarsjs.com/) language. 

The import process will automatically convert your success and failure templates into a new conditionally rendered file. Audit events will appear and behave just as they did in v1.

However, if you plan to use JIT for roles, you'll need to [create new templates](../help-and-support/advanced-help-topics/audit-templates.md) that accommodate role auditing alongside computer auditing. You can use the imported scripts, but they may not contain all the information you expect. Simply create a new email or webhook audit channel, and the new format templates will be pre-filled for you.

### Audit scripts
Changes were also made to the PowerShell audit scripts feature. All your existing scripts will be imported, and will work for computer authorization auditing, as they do today. They will be marked as v1 scripts in the UI.

In order to process JIT for roles events, you'll need to update them to the [new v2 script format](../help-and-support/advanced-help-topics/audit-scripts.md).

Note that support for v1 audit scripts will be removed in a future version of Access Manager.