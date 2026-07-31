{% hint style="warning" icon="clock" %}
**Access Manager v3.0** has been superseded by **v3.1**. This release line reaches end of life on 10th November 2026. [View upgrade guide →](https://go.lithnet.io/hpa0d36k)
{% endhint %}

{% updates format="full" %}

{% update date="2026-07-30" tags="security" %}
## v3.0.1638

{% hint style="warning" icon="shield-halved" %}
This release contains an important security fix. Update recommended.
{% endhint %}

Access Manager v3.0

### Service

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
- Updates third-party components to address security vulnerabilities
- Updates the .NET runtime to the July 2026 security release

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **Improved**
- Adds support for configuring the database backup and maintenance times
- Improves update notification inside the configuration app

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where importing authorization rules resulted in an error
- Fixes an issue where imported authorization rules had no default JIT duration or display name visible in the rules list
- Fixes an issue where authorization rules may not display in the admin UI
- Fixes an issue where the installer failed when .NET 9 or later was installed without .NET 8
- Fixes an error when modifying notification channels using PowerShell
- Fixes an error when setting a notification channel on a role authorization rule using PowerShell
- Fixes an issue where some fields in the configuration app did not refresh when related options changed
- Improves authentication handling on the agent API endpoints

### Agent

#### Windows

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where an agent that had been reset did not resubmit its BitLocker recovery keys, leaving the server without current recovery keys
- Fixes an issue where the installer failed when .NET 9 or later was installed without .NET 8

#### Linux

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
- Updates the .NET runtime to the July 2026 security release

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **Improved**
- Adds support for Ubuntu 26.04

#### macOS

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
- Updates the .NET runtime to the July 2026 security release

<mark style="color:red;"><i class="fa-circle-minus">:circle-minus:</i></mark> **Removed**
- Support for macOS 13 (Ventura) has been removed

### Downloads

- **Service**: [x64](https://packages.lithnet.io/win/access-manager-service/v3.0/x64/LithnetAccessManagerService-3.0.1638.0-x64.exe)
- **Agent**
  - **Windows**: [x64](https://packages.lithnet.io/win/access-manager-agent/v3.0/x64/LithnetAccessManagerAgent-Windows-3.0.1638.0-x64.msi) · [x86](https://packages.lithnet.io/win/access-manager-agent/v3.0/x86/LithnetAccessManagerAgent-Windows-3.0.1638.0-x86.msi) · [arm64](https://packages.lithnet.io/win/access-manager-agent/v3.0/arm64/LithnetAccessManagerAgent-Windows-3.0.1638.0-arm64.msi)
  - **Linux**
    - **Debian / Ubuntu**: [x64](https://packages.lithnet.io/linux/deb/packages/access-manager-agent/v3.0/x64/LithnetAccessManagerAgent3_3.0.1638.0-1_amd64.deb) · [arm64](https://packages.lithnet.io/linux/deb/packages/access-manager-agent/v3.0/arm64/LithnetAccessManagerAgent3_3.0.1638.0-1_arm64.deb)
    - **RHEL / Fedora**: [x64](https://packages.lithnet.io/linux/rpm/packages/access-manager-agent/v3.0/x64/LithnetAccessManagerAgent3-3.0.1638.0-1.x86_64.rpm) · [arm64](https://packages.lithnet.io/linux/rpm/packages/access-manager-agent/v3.0/arm64/LithnetAccessManagerAgent3-3.0.1638.0-1.aarch64.rpm)
    - **Portable (tar.gz)**: [x64](https://packages.lithnet.io/linux/tar/packages/access-manager-agent/v3.0/x64/LithnetAccessManagerAgent3_3.0.1638.0-1_x64.tar.gz) · [arm64](https://packages.lithnet.io/linux/tar/packages/access-manager-agent/v3.0/arm64/LithnetAccessManagerAgent3_3.0.1638.0-1_arm64.tar.gz)
  - **macOS**: [x64](https://packages.lithnet.io/macos/access-manager-agent/v3.0/x64/LithnetAccessManagerAgent-macos-3.0.1638.0-x64.pkg) · [arm64](https://packages.lithnet.io/macos/access-manager-agent/v3.0/arm64/LithnetAccessManagerAgent-macos-3.0.1638.0-arm.pkg)

{% endupdate %}

{% update date="2025-11-07" tags="breaking" %}
## v3.0.1548

{% hint style="danger" icon="triangle-exclamation" %}
This release contains breaking changes. Review the details below before upgrading.
{% endhint %}

Adds markdown rendering for policy messages, new OS support (macOS 26, Debian 13, RHEL 10, Fedora 42), and fixes for Entra hostname resolution, arm64 agent installation, and apt upgrade issues

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for CommonMark markdown rendering in the policy messages shown to users in the web app

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where the service is unable to resolve an Entra hostname with a '$' character in it
- Fixes a NullReferenceException that may occur on a newly built AMS instance

### Agent

#### Windows

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where the Windows x64 agent could be installed on an arm64 machine

#### Linux

<mark style="color:red;"><i class="fa-triangle-exclamation">:triangle-exclamation:</i></mark> **Breaking**
- Updates the Origin and Label fields of the Debian-based repos to Lithnet which will require manual acceptance when upgrading via apt

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for Debian 13
- Adds support for RedHat Enterprise Linux 10
- Adds support for Fedora 42

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where the service unit file was marked as a conf file on Debian-based systems, preventing auto-upgrades via apt

#### macOS

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for macOS 26

{% endupdate %}

{% update date="2025-08-17" tags="feature" %}
## v3.0.1519

Adds preview support for macOS secure token password management, new CLI structure, improved server-side logging, and multiple agent fixes

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Improves server side logging on password provider selection

### Agent

#### Windows

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Added a new command line structure

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS may not be available for up to an hour after the machine boots if the server is not contactable

#### Linux

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Added a new command line structure

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS may not be available for up to an hour after the machine boots if the server is not contactable
- Fixes an issue with integrated windows auth on macOS and Linux

#### macOS

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Added a new command line structure
- Adds preview support for managing the passwords of secure token-enabled accounts on macOS

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS may not be available for up to an hour after the machine boots if the server is not contactable
- Fixes an issue with integrated windows auth on macOS and Linux

{% endupdate %}

{% update date="2025-05-14" tags="maintenance" %}
## v3.0.1325

Fixes LAPS password and BitLocker recovery key reading with Windows Server 2025 DCs, improves LAPS diagnostic logging

### Service

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where Access Manager may be unable to read LAPS passwords or BitLocker recovery keys stored in Active Directory, if a Windows Server 2025 domain controller is in the domain

### Agent

#### Windows

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Improves messages logged when Windows LAPS or legacy LAPS is active on the machine to better identify which policy is active

{% endupdate %}

{% update date="2025-04-06" tags="feature" %}
## v3.0.1312

Fixes NTLM authentication failure preventing agent registration, improves error messages for locked out accounts

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Improves error message shown when a user tries to log in but their AD account is locked out

### Agent

#### Windows

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where NTLM authentication may fail and the agent is unable to register

#### Linux

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where NTLM authentication may fail and the agent is unable to register

#### macOS

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where NTLM authentication may fail and the agent is unable to register

{% endupdate %}

{% update date="2025-03-07" tags="maintenance" %}
## v3.0.1309

Fixes authorization rule display, RapidLAPS audit logging, cache clearing, and adds rate limiting

### Service

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where a computer authorization rule may not show the display name when viewed via PowerShell
- Fixes an issue where RapidLAPS authorization failures do not show the type of RapidLAPS request in the log or audit event data sets
- Fixes an issue where deleting the final authorization rule in the list would not clear the rule from the cache
- Adds rate limiting to RapidLAPS PIN entry requests

{% endupdate %}

{% update date="2025-01-31" tags="feature" %}
## v3.0.1302

Major authorization rule improvements, PowerShell remoting support, and multiple bug fixes

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- JIT computer and role access times can now be selected in days/hours/minutes
- Computer and role authorization rule lists are now full-text searchable
- Computer and role authorization rules now save immediately after editing
- Re-architects computer and role authorization rules to better support instances with thousands of rules
- Adds support for enterprise customers to be able to manage the service via PowerShell remoting
- Improves content security policy and permission policy on the web app

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where editing a role changes its position in the list
- Fixes an issue where searching on a role name did not return expected results
- Fixes an issue where searching on a role CSV export did not contain all details
- Fixes a UI crash when editing a password generation policy, but providing an invalid combination of settings
- Fixes an issue where the AD JIT group creation job can get stuck in a broken state
- Fixes validation logic on Splunk hostname
- Fixes an issue where an internal error in the web app redirects to a 404 page

{% endupdate %}

{% update date="2024-11-12" tags="feature" %}
## v3.0.1270

Adds OIDC/WS-Federation claim mapping and PowerShell audit improvements; fixes RapidLAPS upgrade issue, high CPU on Windows 24H2, and switches logs to UTC

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds a new -ForceFullSync parameter to the Set-AmsActiveDirectoryJitGroupCreationRule cmdlet
- Adds support for automatically mapping OpenID Connect and WS-Federation claims for sid and onprem_sid
- Adds new cmdlets for modifying OpenID Connect and WS-Federation claim mappings
- Adds event logging for the use of the Get-AmsLocalAdminPassword cmdlets

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where the Request.Target parameter was null on a PowerShell audit request
- Fixes an issue where the button to select the custom logo displayed by the web app could not be clicked with the mouse
- Fixes an issue where changing settings on AD JIT Group creation rule doesn't trigger a restart

### Agent

#### Windows

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS may not work after performing an in-place agent upgrade to v3.0.1257
- Modifies log files to be in UTC time
- Fixes an issue where the Access Manager agent can cause high CPU consumption on the logon screen on Windows 24H2 builds

#### Linux

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS may not work after performing an in-place agent upgrade to v3.0.1257
- Modifies log files to be in UTC time

#### macOS

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS may not work after performing an in-place agent upgrade to v3.0.1257
- Modifies log files to be in UTC time

{% endupdate %}

{% update date="2024-10-09" tags="feature" %}
## v3.0.1257

Adds web app tab visibility control, JIT group cmdlets, macOS 15 support, HTTPS port configuration, and fixes for authorization rules and Windows 11 24H2 RapidLAPS

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds an option to the Get-AmsLocalAdminPassword cmdlet to get all active passwords from all providers
- Adds support for hiding the various tabs in the web app (Enterprise edition feature)
- Adds new cmdlets for adding JIT group creation rules via PowerShell

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where an error occurs in the web app when approving a RapidLAPS request without providing a mandatory reason
- Fixes an issue with the Get-AmsFveRecoveryKey cmdlet
- Fixes an issue where a PowerShell authorization rule could crash the Access Manager service
- Fixes an issue where agents < v3.0.1229 with server version v3.0.1229 may change their passwords too frequently

### Agent

#### Windows

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for specifying the HTTPS port on the agent configuration command line

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS elevation requests on the RTM version of Windows 11 24H2 would fail

#### Linux

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for specifying the HTTPS port on the agent configuration command line

#### macOS

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for specifying the HTTPS port on the agent configuration command line
- Adds support for macOS 15-based agents

{% endupdate %}

{% update date="2024-09-11" tags="feature" %}
## v3.0.1229

Adds Windows 11 24H2 support, rollback detection, license file loading, and multiple service and agent fixes

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for offering both negotiate and NTLM authentication to web clients
- Adds support for loading licenses from files

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where RapidLAPS elevation requests coming from Windows 11 24H2 builds could not be approved
- Fixes an issue where the installer would fail when a protected connection string was in use
- Fixes an issue where Negotiate authentication was used even when basic or NTLM authentication was selected
- Fixes an issue where the 'specific site' or 'specific DC' options on a JIT computer authorization rule were not respected
- Fixes an issue where a computer JIT fulfillment operation would target a DC in the AMS server's site
- Fixes an issue where an agent installed on the same machine as the AMS server could not register
- Fixes an issue where DC check in details are not processed for hybrid-joined devices

### Agent

#### Windows

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for detecting rollback events on clients and initiating a password re-sync operation
- Adds support for Windows 11 24H2 based agents

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where agent-side issues such as untrusted server certificate or incorrect hostname were missing from the logs
- Fixes an issue where RapidLAPS elevation details from Windows 11 24H2 clients was incomplete

#### Linux

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for detecting rollback events on clients and initiating a password re-sync operation

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where agent-side issues such as untrusted server certificate or incorrect hostname were missing from the logs

#### macOS

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for detecting rollback events on clients and initiating a password re-sync operation

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where agent-side issues such as untrusted server certificate or incorrect hostname were missing from the logs

{% endupdate %}

{% update date="2024-08-19" tags="maintenance" %}
## v3.0.1218

Fixes an issue where community edition users may receive an error when using RapidLAPS

### Service

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where community edition users may receive an error when trying to use RapidLAPS

{% endupdate %}

{% update date="2024-08-17" tags="feature" %}
## v3.0.1217

Fixes WS-Federation authentication, RapidLAPS UI prompt duplication, and adds QR code support for passwords and recovery keys

### Service

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Adds support for showing LAPS passwords and BitLocker recovery keys as QR codes

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where users could not authenticate with WS-Federation
- Fixes an issue where RapidLAPS UI prompts set in the default policy would duplicate

{% endupdate %}

{% update date="2024-08-06" tags="maintenance" %}
## v3.0.1210

Fixes Windows authentication when only Windows auth is enabled

### Service

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where agents using Windows auth couldn't authenticate if only Windows authentication was enabled

{% endupdate %}

{% update date="2024-07-29" tags="feature" %}
## v3.0.1206

Initial release of Access Manager v3.0

### Agent

#### Windows

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Initial release

#### Linux

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Initial release

#### macOS

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **New**
- Initial release

{% endupdate %}

{% endupdates %}