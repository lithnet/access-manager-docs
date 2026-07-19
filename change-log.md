{% updates format="full" %}

{% update date="2026-07-19" tags="breaking,security" %}
## v3.1.1089

{% hint style="danger" icon="triangle-exclamation" %}
This release contains breaking changes. Review the details below before upgrading.
{% endhint %}

Access Manager v3.1

### Service

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
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

<mark style="color:blue;"><i class="fa-arrow-right-arrow-left">:arrow-right-arrow-left:</i></mark> **Changed**
- Access Manager now runs on .NET 10

### Agent

#### Windows

<mark style="color:red;"><i class="fa-triangle-exclamation">:triangle-exclamation:</i></mark> **Breaking**
- The Windows agent is no longer available for 32-bit (x86) versions of Windows
- The Windows agent is no longer available for Windows 10

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where an agent that had been reset did not resubmit its BitLocker recovery keys, leaving the server without current recovery keys
- Fixes an issue where the installer failed when .NET 9 or later was installed without .NET 8

#### Linux

<mark style="color:red;"><i class="fa-triangle-exclamation">:triangle-exclamation:</i></mark> **Breaking**
- The Linux agent is no longer available for Debian 11, Ubuntu 20.04, and Fedora 38 to 41

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
- Updates the .NET runtime to the July 2026 security release

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **Improved**
- Adds support for Ubuntu 26.04
- Adds support for Fedora 43 and Fedora 44

<mark style="color:blue;"><i class="fa-arrow-right-arrow-left">:arrow-right-arrow-left:</i></mark> **Changed**
- Access Manager now runs on .NET 10

#### macOS

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
- Updates the .NET runtime to the July 2026 security release

<mark style="color:blue;"><i class="fa-arrow-right-arrow-left">:arrow-right-arrow-left:</i></mark> **Changed**
- Access Manager now runs on .NET 10

<mark style="color:red;"><i class="fa-circle-minus">:circle-minus:</i></mark> **Removed**
- Support for macOS 13 (Ventura) has been removed

### Downloads

- **Service** — [x64](https://packages.lithnet.io/win/access-manager-service/v3.1/x64/LithnetAccessManagerService-3.1.1089.0-x64.exe)
- **Agent**
  - **Windows** — [x64](https://packages.lithnet.io/win/access-manager-agent/v3.1/x64/LithnetAccessManagerAgent-Windows-3.1.1089.0-x64.msi) · [arm64](https://packages.lithnet.io/win/access-manager-agent/v3.1/arm64/LithnetAccessManagerAgent-Windows-3.1.1089.0-arm64.msi)
  - **Linux**
    - **Debian / Ubuntu** — [x64](https://packages.lithnet.io/linux/deb/packages/access-manager-agent/v3.1/x64/LithnetAccessManagerAgent3_3.1.1089.0-1_amd64.deb) · [arm64](https://packages.lithnet.io/linux/deb/packages/access-manager-agent/v3.1/arm64/LithnetAccessManagerAgent3_3.1.1089.0-1_arm64.deb)    - **RHEL / Fedora** — [x64](https://packages.lithnet.io/linux/rpm/packages/access-manager-agent/v3.1/x64/LithnetAccessManagerAgent3-3.1.1089.0-1.x86_64.rpm) · [arm64](https://packages.lithnet.io/linux/rpm/packages/access-manager-agent/v3.1/arm64/LithnetAccessManagerAgent3-3.1.1089.0-1.aarch64.rpm)    - **Portable (tar.gz)** — [x64](https://packages.lithnet.io/linux/tar/packages/access-manager-agent/v3.1/x64/LithnetAccessManagerAgent3_3.1.1089.0-1_x64.tar.gz) · [arm64](https://packages.lithnet.io/linux/tar/packages/access-manager-agent/v3.1/arm64/LithnetAccessManagerAgent3_3.1.1089.0-1_arm64.tar.gz)
  - **macOS** — [x64](https://packages.lithnet.io/macos/access-manager-agent/v3.1/x64/LithnetAccessManagerAgent-macos-3.1.1089.0-x64.pkg) · [arm64](https://packages.lithnet.io/macos/access-manager-agent/v3.1/arm64/LithnetAccessManagerAgent-macos-3.1.1089.0-arm.pkg)

{% endupdate %}

{% endupdates %}