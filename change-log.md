{% hint style="warning" icon="clock" %}
**** has been superseded by **v3.1**. This release line reaches end of life on 10th November 2026. [View upgrade guide →](https://go.lithnet.io/x78nz34b)
{% endhint %}

{% updates format="full" %}

{% update date="2026-07-30" tags="security" %}
## v2.1.1069

{% hint style="warning" icon="shield-halved" %}
This release contains an important security fix. Update recommended.
{% endhint %}

Access Manager v2.1

### Service

<mark style="color:orange;"><i class="fa-shield-halved">:shield-halved:</i></mark> **Security**
- Updates third-party components to address security vulnerabilities
- Updates the .NET runtime to the July 2026 security release

<mark style="color:green;"><i class="fa-sparkles">:sparkles:</i></mark> **Improved**
- Improves update notification inside the configuration app

### Downloads

- **Service**: [x64](https://packages.lithnet.io/win/access-manager-service/v2.1/x64/LithnetAccessManagerService-2.1.1069.0-x64.exe)

{% endupdate %}

{% update date="2024-11-19" tags="maintenance" %}
## v2.1.1032

Fixes an issue where the installer would not run without internet access

### Service

<mark style="color:blue;"><i class="fa-wrench">:wrench:</i></mark> **Fixed**
- Fixes an issue where the installer would not run if the machine did not have internet access

{% endupdate %}

{% update date="2024-10-18" tags="breaking" %}
## v2.1.1029

{% hint style="danger" icon="triangle-exclamation" %}
This release contains breaking changes. Review the details below before upgrading.
{% endhint %}

Migrates to .NET 8 runtimes for service and all agents; arm32 Linux builds discontinued

### Service

<mark style="color:red;"><i class="fa-triangle-exclamation">:triangle-exclamation:</i></mark> **Breaking**
- .NET 8 ASP.NET and Desktop runtimes are now required to install the Access Manager Service

### Agent

#### Windows

<mark style="color:blue;"><i class="fa-arrow-right-arrow-left">:arrow-right-arrow-left:</i></mark> **Changed**
- The arm64 build of the Windows agent now uses .NET Framework 4.8.1, rather than .NET Core

#### Linux

<mark style="color:red;"><i class="fa-triangle-exclamation">:triangle-exclamation:</i></mark> **Breaking**
- .NET 8 is now used for the Linux agents. Due to .NET compatibility issues, arm32 builds are no longer supported

#### macOS

<mark style="color:blue;"><i class="fa-arrow-right-arrow-left">:arrow-right-arrow-left:</i></mark> **Changed**
- .NET 8 is now used for the macOS agents

{% endupdate %}

{% endupdates %}