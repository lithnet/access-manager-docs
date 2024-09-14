# Internet access requirements

## Access Manager Service installer
The Access Manager service installer can be operated offline, however, it does require downloading and installing the following dependencies
- [.NET Desktop Runtime](https://dotnet.microsoft.com/download/dotnet-core/8.0/runtime) 8.0.8 or later installed
- [.NET Hosting Bundle](https://dotnet.microsoft.com/download/dotnet-core/8.0/runtime) 8.0.8 or later installed

If you plan to use an SQL Express database, then you also need to [download the SQL Express installer](https://download.microsoft.com/download/7/c/1/7c14e92e-bdcb-4f89-b7cf-93543e7112d1/SQLEXPR_x64_ENU.exe) - however, do not install it manually. Copy the file to the server, and the installer will prompt you for the location of the installer, so it can perform the installation using the correct parameters. Installing SQL express manually will result in certain features like backup capability being broken.

For the installer to download the necessary prerequisites itself, the following hosts must be contactable.
| Capability | Destination host | Destination ports |
| --- | --- | --- |
| .NET runtimes | download.visualstudio.microsoft.com | TCP 443 |
| SQL Express | download.microsoft.com | TCP 443 |

## Access Manager Service

Internet access is not required for the Access Manager service to operate, unless you want to use the features below

| Capability | Destination host | Destination ports |
| --- | --- | --- |
| Be notified when new updates are available for the Access Manager service | packages.lithnet.io | TCP 443 |
| Enable devices to authenticate to the Access Manager API | graph.microsoft.com login.microsoftonline.com | TCP 443 |
| Azure AD authentication for end users | login.microsoftonline.com | TCP 443 |
| OpenID Connect authentication | The hostname specified in the issuer/authority field of the OIDC setup page | TCP 443 |

## Access Manager Agent

The Access Manager agent does not have any internet access requirements.