# Change log
## v2.0.9430 20th June 2023
### Access Manager Service
- \[FIX\] Fixes an issue where an error message appears after clicking on the help link in the Azure AD tenant information screen
- \[UPDATE\] Updates installer .NET package prerequisites to 6.0.18

### Access Manager Agent
- \[UPDATE\] Updates macOS and Linux agents with latest .NET dependencies
- \[FIX\] Updates logic to prevent the Access Manager Agent from starting when Windows LAPS is in use
- \[FIX\] Fixes an issue where the agent is unable to change the local admin password when the 'Server' service is disabled

## v2.0.9427 11th June 2023
### Access Manager Service
- \[FIX\] Fixes an issue when exporting permissions that would result in target names being exported as SIDs instead of friendly names 
- \[FIX\] Fixes an issue where a recently re-imaged machine with the Access Manager agent may not change its password until the next scheduled check in time

## v2.0.9424 6th June 2023
### Access Manager Service
- \[FIX\] Fixes an issue where the web UI reports that an Azure AD device does not have a LAPS password
- \[FIX\] Fixes an issue where the installer was unable to validate an Azure SQL connection string

## v2.0.2422 9th May 2023
### Access Manager Service
- \[FEATURE\] Adds support for reading Windows LAPS passwords from Azure AD

## v2.0.2420 14th April 2023
### Access Manager Service
- \[FIX\] Fixes an issue decrypting Windows LAPS passwords

## v2.0.2419 11th Apr 2023
### Access Manager Service
- \[FEATURE\] Allows community edition to access encrypted Windows LAPS passwords

## v2.0.9417 27th Feb 2023
### Access Manager Service
- \[FIX\] Fixes an issue where agents behind a reverse proxy may not be able to change their local admin passwords. Note both the agent and server must be running at least v2.0.9417

### Access Manager Agent
- \[FIX\] Fixes an issue where agents behind a reverse proxy may not be able to change their local admin passwords. Note both the agent and server must be running at least v2.0.9417
- \[FIX\] Fixes an issue where Windows agents do not start if the `Server` service is disabled.

## v2.0.9412 18th Feb 2023
### Access Manager Service
- \[FIX\] Fixes an issue where the JIT group creation service would not create groups where multiple rules were configured pointing to the same source OU

## v2.0.9411 9th Feb 2023
### Access Manager Service
- \[FIX\] Fixes an issue where searching for a computer in a different forest by its DNS name would not work
- \[FIX\] Fixes an issue where an error message would be shown in the UI when there was no certificate configuration deployed to Active Directory

## v2.0.9410 1st Feb 2023
### Access Manager Service
- \[FIX\] Fixes an issue where the effective access calculator would show 'access denied' for LAPS history when an enterprise license was not present
- \[FIX\] Fixes an issue where changes to the JIT group creation settings do not trigger a restart required message
- \[FIX\] Fixes an issue where upgrading from v1.1 to v2.0 may fail
- \[FIX\] Fixes an issue where you cannot JIT into a group that contains a slash character
- \[FIX\] Fixes an issue where AMS-managed device password history was not purged according to policy settings
- \[FEATURE\] Adds support for using certificate authentication when Access Manager is behind a load balancer
- \[FEATURE\] Adds additional UI helpers for common agent and API misconfigurations
- \[FEATURE\] Adds the ability to target a JIT role operation against a specific site or a specific DC

### Access Manager Agent
- \[FEATURE\] Improves logging for agent-side issues such as server name misconfigurations, registration modes not being enabled, and API not being enabled

## v2.0.9399 8th December 2022
### Access Manager Service
- \[FIX\] Fixes an issue where the SQL express installer does not execute when upgrading from v1.x and using the manual download option

## v2.0.9395 4th December 2022
### Access Manager Service
- \[FIX\] Fixes an issue where API authentication fails if the server and client are configured with host names differing by case
- \[FIX\] Fixes an issue where the installer would continue the installation if the SQL Express installer failed, leading to an incomplete installation
- \[FIX\] Fixes an issue where saving the config without a TLS certificate results in an "Object reference not set to an instance of an object" error
- \[FIX\] Enables installer logging by default. Installer will create an MSIxxx.log file in %localappdata%\temp
- \[FIX\] Fixes an issue where smart-card authentication would not work after upgrading from v1 to v2
- \[FIX\] Fixes an issue where permissions for AMS admins group were missing from the registry
- \[FIX\] Fixes an issue where the JIT group targeting algorithm may not select the correct DC, resulting in delays accessing servers after a successful JIT operation
- \[FEATURE\] Modifies the silent installer for Windows to not require command line parameters to configure it for AD mode, allowing for a simpler deployment via group policy
- \[FEATURE\] Updates PowerShell diagnostic cmdlet to include logs as well as config
- \[FEATURE\] Adds the ability to generate a diagnostic log package from the 'Help' page in the config app
- \[FEATURE\] The roles list is now free-text searchable

### Access Manager Agent
- \[FIX\] Fixes an issue where API authentication fails if the server and client are configured with host names differing by case
- \[FIX\] Allows silent installation of Windows agent to default to AD mode without requiring MSI transforms or parameters

## v2.0.9376 18th November 2022
### Access Manager Service
- \[FIX\] Fixes an issue where the service incorrectly goes into recovery mode when the November 2022 Windows updates are applied to a DC and the [known issue](https://support.microsoft.com/en-us/topic/kb5021131-how-to-manage-the-kerberos-protocol-changes-related-to-cve-2022-37966-fd837ac3-cdec-4e76-a6ec-86e67501407d#knownissues5021131) regarding RC4 is in play. Now the service will instead just terminate with a message that domain connectivity is not available.

## v2.0.9375 15th November 2022
### Access Manager Service
- \[FIX\] Fixes an issue where the service installer may fail on a non-English language Windows system
- \[FIX\] Fixes an issue where the New-AmsComputerAuthorizationRule and Set-AmsComputerAuthorizationRule report an error

## v2.0.9373 10th November 2022
### Access Manager Service
- \[SECURITY FIX\] Updates the SQL client libraries to resolve [CVE 2022-41064](https://github.com/dotnet/announcements/issues/239)

## v2.0.9371 7th November 2022
- Initial release of v2. Review the [what's new in v2 article](./whats-new.md) to learn about the major changes since Access Manager v1