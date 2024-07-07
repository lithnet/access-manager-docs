# Installing the Access Manager Agent on Windows

## Prerequisites

In order to install the Access Manager Agent, the following prerequisites must be met

1. Windows 10 or Windows Server 2016 or later
2. [.NET Framework Runtime](https://dotnet.microsoft.com/download) 4.7.2 or later installed for x86 and x64 versions of Windows
2. [.NET Framework Runtime](https://dotnet.microsoft.com/download) 4.8.1 or later installed for arm64 versions of Windows

We recommend using a configuration management tool such as SCCM to deploy the agent to your fleet.

## Determine your authentication mode

Active Directory-joined devices can use their machine identity to automatically authenticate to the AMS server.

Microsoft Entra-joined devices can use their Entra certificate to automatically authenticate to the AMS server. 

Other devices must use a registration key, obtained from the AMS server to authenticate. These devices will create their own authentication certificate, and use the registration key a single time, to register their certificate with the server. Once this is successful, they will no longer need the registration key, and it will be deleted from the system.

## Download and install the Access Manager Agent

1. Download the latest version of the agent from the [downloads](../downloads.md) page. Take note that you must install the x64 version on 64-bit machines, and the x86 version on 32-bit machines.
2. Run the agent installation package. When prompted, enter the server name, and choose the registration mode you'd like to use for the agent

{% hint style="warning" %}
If the hostname provided does not match exactly the `External host name` value configured on the [Host configuration page](../../help-and-support/app-pages/host-configuration-page.md), the agent will fail to connect to the server
{% endhint %}

## Deploying the agent silently

You can install the MSI packages silently using the following command lines

### Silent installation for domain-joined Windows devices

Use the following command line to install the agent in Active Directory authentication mode

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AUTHMODE=1 SERVER=ams.lithnet.local 
```

### Silent installation for Microsoft Entra-joined devices

Use the following command line to install the agent in Microsoft Entra mode, replacing the `SERVER`  value as appropriate

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AUTHMODE=2 SERVER=ams.lithnet.local 
```

### Silent installation for standalone Windows devices

Use the following command line to install the agent in AMS registration mode, replacing the `SERVER` and `REGISTRATIONKEY` values are appropriate

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AUTHMODE=4 SERVER=ams.lithnet.local REGISTRATIONKEY=XXXX
```

## Validate agent installation

On the Access Manager server, go to the `Access Manager Agent/Devices` page, and ensure that the devices you installed the agent on have appeared in the device list. If you configured your registration key to require manual approval, you must approve the devices before they can be accessed.

## Viewing log files

Basic logs entries can be viewed using the Windows Event Viewer, but more detailed log information can be found in `%ProgramFiles%\Lithnet\Access Manager Agent\logs`

## Reconfiguring the agent

If you need to change the agent configuration, you can do so at any time by running 

```batch
"%ProgramFiles%\Lithnet\Access Manager Agent\Lithnet.AccessManager.Agent.exe" --setup
```

