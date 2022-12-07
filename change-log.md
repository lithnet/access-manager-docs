# Change log

## v2.0.9399 8th December 2022
### Access Manager Service
- [FIX] Fixes an issue where the SQL express installer does not execute when upgrading from v1.x and using the manual download option

## v2.0.9395 4th December 2022
### Access Manager Service
- [FIX] Fixes an issue where API authentication fails if the server and client are configured with host names differing by case
- [FIX] Fixes an issue where the installer would continue the installation if the SQL Express installer failed, leading to an incomplete installation
- [FIX] Fixes an issue where saving the config without a TLS certificate results in an "Object reference not set to an instance of an object" error
- [FIX] Enables installer logging by default. Installer will create an MSIxxx.log file in %localappdata%\temp
- [FIX] Fixes an issue where smart-card authentication would not work after upgrading from v1 to v2
- [FIX] Fixes an issue where permissions for AMS admins group were missing from the registry
- [FIX] Fixes an issue where the JIT group targeting algorithm may not select the correct DC, resulting in delays accessing servers after a successful JIT operation
- [FEATURE] Modifies the silent installer for Windows to not require command line parameters to configure it for AD mode, allowing for a simpler deployment via group policy
- [FEATURE] Updates PowerShell diagnostic cmdlet to include logs as well as config
- [FEATURE] Adds the ability to generate a diagnostic log package from the 'Help' page in the config app
- [FEATURE] The roles list is now free-text searchable

### Access Manager Agent
- [FIX] Fixes an issue where API authentication fails if the server and client are configured with host names differing by case
- [FIX] Allows silent installation of Windows agent to default to AD mode without requiring MSI transforms or parameters

## v2.0.9376 18th November 2022
### Access Manager Service
- [FIX] Fixes an issue where the service incorrectly goes into recovery mode when the November 2022 Windows updates are applied to a DC and the [known issue](https://support.microsoft.com/en-us/topic/kb5021131-how-to-manage-the-kerberos-protocol-changes-related-to-cve-2022-37966-fd837ac3-cdec-4e76-a6ec-86e67501407d#knownissues5021131) regarding RC4 is in play. Now the service will instead just terminate with a message that domain connectivity is not available.

## v2.0.9375 15th November 2022
### Access Manager Service
- [FIX] Fixes an issue where the service installer may fail on a non-english language Windows system
- [FIX] Fixes an issue where the New-AmsComputerAuthorizationRule and Set-AmsComputerAuthorizationRule report an error

## v2.0.9373 10th November 2022
### Access Manager Service
- [SECURITY FIX] Updates the SQL client libraries to resolve [CVE 2022-41064](https://github.com/dotnet/announcements/issues/239)

## v2.0.9371 7th November 2022
- Initial release of v2. Review the [what's new in v2 article](./whats-new.md) to learn about the major changes since Access Manager v1