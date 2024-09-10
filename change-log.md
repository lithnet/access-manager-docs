# Change log
## v3.0.1227 11th September 2024
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