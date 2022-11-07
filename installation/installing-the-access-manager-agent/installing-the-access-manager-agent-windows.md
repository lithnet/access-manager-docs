# Installing the Access Manager Agent on Windows

## Prerequisites

In order to install the Access Manager Agent, the following prerequisites must be met

1. Windows 8.1 or Windows Server 2012 R2 or later
2. [.NET Framework Runtime](https://dotnet.microsoft.com/download) 4.7.2 or later installed

We recommend using a configuration management tool such as SCCM to deploy the agent to your fleet.

## Determine your password storage mode

The Access Manager Agent can store passwords in Active Directory, or in the AMS directory. Password storage in the Active Directory is only available for domain-joined clients, and requires [schema extensions to the Active Directory](../../configuration/deploying-features/setting-up-lithnet-laps/).

Azure AD devices, and standalone non-domain-joined devices always use the AMS directory to store passwords.

| Machine state                      | Password storage location |
| ---------------------------------- | ------------------------- |
| Domain-joined                      | Active Directory          |
| Azure AD-joined                    | AMS directory             |
| Azure AD-registered                | AMS directory             |
| Not joined to a domain or Azure AD | AMS directory             |

## Determine your authentication mode

When using the AMS directory to store passwords, you must determine what authentication mode you are going to use.

Azure AD-joined and registered devices, can use their Azure AD certificate to automatically authenticate to the AMS server. You'll need the Azure AD tenant ID to configure Azure AD auth.

Other devices must use a registration key, obtained from the AMS server to authentication. These devices will create their own authentication certificate, and use the registration key a single time, to register their certificate with the server. Once this is successful, they will no longer need the registration key, and it will be deleted from the system.

## Download and install the Access Manager Agent

1. Download the latest version of the agent from the [releases](https://github.com/lithnet/access-manager/releases/latest) page. Take note that you must install the x64 version on 64-bit machines, and the x86 version on 32-bit machines.
2. Run the AMA installation package. When prompted, choose the password storage location appropriate for your environment.
3. If you are using the AMS directory, you'll be prompted to select the authentication type you'd like to use. You can use Azure AD authentication, if the agent is running on a Windows 10 Azure AD joined or registered device. If the installer can detect the Azure tenant ID from the workstation's join information, it will be pre-populated here. Otherwise, you'll need to provide the tenant ID yourself.

```
If your device is not Azure AD joined or registered, you'll need to use a registration key to authenticate the agent to the AMS server. 
```

1. If you are using the agent in Active Directory mode, you'll need to configure the agent via a group policy. Follow the [setup guide for Lithnet LAPS for Active Directory](../../configuration/deploying-features/setting-up-lithnet-laps/setting-up-lithnet-laps-for-active-directory.md) for the correct process of setting up the relevant group policy settings. Agents using AMS directory mode get their password policy from the AMS server, and do not use group policy at all.

## Deploying the agent silently

You can install the MSI packages silently using the following command lines

### Silent installation in Active Directory password storage mode

Use the following command line to install the agent in Active Directory mode

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AMSSERVERENABLED=0 AUTHMODE=0
```

### Silent installation for Azure AD-joined and registered devices

Use the following command line to install the agent in Azure AD mode, replacing the `SERVER` and `AZUREADTENANTID` values are appropriate

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AMSSERVERENABLED=1 AUTHMODE=2 SERVER=ams.lithnet.local AZUREADTENANTID=YYYY
```

### Silent installation for standalone Windows devices

Use the following command line to install the agent in AMS directory mode, replacing the `SERVER` and `REGISTRATIONKEY` values are appropriate

```
msiexec /i Lithnet.AccessManager.Agent.msi /qn AMSSERVERENABLED=1 AUTHMODE=4 SERVER=ams.lithnet.local REGISTRATIONKEY=XXXX
```

## Viewing log files

Basic logs entries can be viewed using the Windows Event Viewer, but more detailed log information can be found in `%ProgramFiles%\Lithnet\Access Manager Agent\logs`

## Reconfiguring the agent

If you need to change the agent configuration, you can do so at any time by running 

```batch
"%ProgramFiles%\Lithnet\Access Manager Agent\Lithnet.AccessManager.Agent.exe" --setup
```

