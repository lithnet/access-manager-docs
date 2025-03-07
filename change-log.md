# Change log

## v3.0.1309 7th March 2025
### Access Manager service
- \[FIX\] Fixes an issue a computer authorization rule may not show the display name when viewed via PowerShell
- \[FIX\] Fixes an issue RapidLAPS authorization failures do not show the type of RapidLAPS request in the log or audit event data sets
- \[FIX\] Fixes an issue where deleting the final authorization rule in the list would not clear the rule from the cache
- \[FIX\] Adds rate limiting to RapidLAPS PIN entry requests

## v3.0.1302 30th January 2025
### Access Manager service
- \[FEATURE\] JIT computer and role access times can now be selected in days/hours/minutes
- \[FEATURE\] Computer and role authorization rule lists are now full-text searchable
- \[FEATURE\] Computer and role authorization rules now save immediately after editing. There is no need to 'save' the global config to commit the rule changes
- \[FEATURE\] Re-architects computer and role authorization rules to better support instances with thousands of rules
- \[FEATURE\] Adds support for enterprise customers to be able to manage the service via PowerShell remoting
- \[FEATURE\] Improves content security policy and permission policy on the web app

- \[FIX\] Fixes an issue where editing a role changes its position in the list
- \[FIX\] Fixes an issue where searching on a role name did not return expected results
- \[FIX\] Fixes an issue where searching on a role CSV export did not contain all details
- \[FIX\] Fixes an UI crash when editing a password generation policy, but providing an invalid combination of settings
- \[FIX\] Fixes an issue where the AD JIT group creation job can get stuck in a broken state and not create any new groups
- \[FIX\] Fixes validation logic on splunk hostname
- \[FIX\] Fixes an issue were an internal error in the web app redirects to a 404 page

## v3.0.1270 13th November 2024
### Access Manager service
- \[FIX\] Fixes an issue where the `Request.Target` parameter was null on a PowerShell audit request
- \[FIX\] Modifies log files to be in UTC time
- \[FIX\] Fixes an issue where the button to select the custom logo displayed by the web app could not be clicked with the mouse
- \[FIX\] Fixes an issue where changing settings on AD JIT Group creation rule doesn't trigger a re-sync
- \[FEATURE\] Adds a new `-ForceFullSync` parameter to the `Set-AmsActiveDirectoryJitGroupCreationRule` cmdlet
- \[FEATURE\] Adds support for automatically mapping OpenID Connect and WS-Federation claims for `sid` and `onprem_sid`, in addition to the default value of `upn`. SID claims will take precedence over UPN claims due to their immutability.
- \[FEATURE\] Adds new [cmdlets](/help-and-support/powershell-help/Add-AmsIdpClaimMapping.md) for modifying OpenID Connect and WS-Federation claim mappings. You can now use custom attributes instead of `upn` for mapping to Active Directory users
- \[FEATURE\] Adds event logging for the use of the `Get-AmsLocalAdminPassword` cmdlets

### Access Manager agent
- \[FIX\] Fixes an issue where RapidLAPS may not working after performing an in-place agent upgrade to v3.0.1257
- \[FIX\] Fixes an issue where the Access Manager agent can cause high CPU consumption on the logon screen on Windows 24H2 builds
- \[FIX\] Modifies log files to be in UTC time

## v3.0.1257 9th October 2024
### Access Manager service
- \[FIX\] Fixes an issue where an error occurs in the web app when approving a RapidLAPS request without providing a mandatory reason
- \[FIX\] Fixes an issue with the Get-AmsFveRecoveryKey cmdlet
- \[FIX\] Fixes an issue where a PowerShell authorization rule could crash the Access Manager service
- \[FIX\] Fixes an issue where agents < v3.0.1229 with server version v3.0.1229 may change their passwords too frequently
- \[FEATURE\] Adds an option to the Get-AmsLocalAdminPassword cmdlet to get all active passwords from all providers
- \[FEATURE\] Adds support for hiding the various tabs in the web app (Enterprise edition feature)
- \[FEATURE\] Adds new cmdlets for adding JIT group creation rules via PowerShell

### Access Manager agent
- \[FIX\] Fixes an issue where RapidLAPS elevation requests on the RTM version of Windows 11 24H2 would fail to launch the elevated process
- \[FEATURE\] Adds support for macOS 15-based agents
- \[FEATURE\] Adds support for specifying the HTTPS port on the agent configuration command line

## v3.0.1229 11th September 2024
### Access Manager service
- \[FEATURE\] Adds support for Windows 11 24H2 based agents
- \[FEATURE\] Adds support for offering both negotiate and NTLM authenticate to web clients
- \[FEATURE\] Adds support for detecting rollback events on clients and initiating a password re-sync operation
- \[FEATURE\] Adds support for loading licenses from files

- \[FIX\] Fixes an issue where RapidLAPS elevation requests coming from Windows 11 24H2 builds could not be approved
- \[FIX\] Fixes an issue where the installer would fail when a protected connection string was in use
- \[FIX\] Fixes an issue where Negotiate authentication was used even when basic or NTLM authentication was selected
- \[FIX\] Fixes an issue where the 'specific site' or 'specific DC' options on a JIT computer authorization rule were not respected
- \[FIX\] Fixes an issue where a computer JIT fulfillment operation would target a DC in the AMS server's site, rather that the target computer's site
- \[FIX\] Fixes an issue where an agent installed on the same machine as the AMS server could not register with Windows authentication
- \[FIX\] Fixes an issue where DC check in details are not processed for hybrid-joined devices

### Access Manager agent
- \[FEATURE\] Adds support for detecting rollback events on clients and initiating a password re-sync operation
- \[FEATURE\] Adds support for Windows 11 24H2 based agents

- \[FIX\] Fixes an issue where RapidLAPS elevation details from Windows 11 24H2 clients was incomplete
- \[FIX\] Fixes an issue where agent-side issues such as untrusted server certificate or incorrect hostname were missing from the logs and misinterpreted as an 'API not reachable' error


## v3.0.1218 19th August 2024
### Access Manager service
- \[FIX\] Fixes an issue where community edition users may receive and error when trying to use RapidLAPS

## v3.0.1217 17th August 2024
### Access Manager service
- \[FIX\] Fixes an issue where users could not authenticate with WS-Federation
- \[FIX\] Fixes an issue where RapidLAPS UI prompts set in the default policy would duplicate
- \[FEATURE\] Adds support for showing LAPS passwords and BitLocker recovery keys as QR codes that can be scanned with a 2D barcode scanner. (Enterprise edition feature)


## v3.0.1210 6th August 2024
### Access Manager service
- \[FIX\] Fixes an issue where agents using windows auth couldn't authenticate if only windows authentication was enabled in the agent registration config

## v3.0.1206 30th July 2024
- Initial release.

Review the [what's new in v3 article](./whats-new.md) to learn about the major changes since Access Manager v2.

## Previous versions
Change log for [Access Manager version 2](https://docs.lithnet.io/ams/v2.0/change-log)