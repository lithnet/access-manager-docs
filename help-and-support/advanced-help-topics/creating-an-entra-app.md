# Creating an Entra app for Access Manager

If you are going to be using Entra to authenticate users with OpenID Connect, if you want to access LAPS passwords stored in Entra ID, or you want to install the Lithnet Access Manager agent on Entra-joined devices, you'll need to create an app registration for Access Manager in your Entra ID portal.

You only need a single app registration for the Access Manager instance. Just ensure that you grant the appropriate directory permissions for the scenarios you want to support.

# Step 1: Configure a new application in Entra ID

1. Log into portal.azure.com with administrative credentials, select `More services` and select `Microsoft Entra ID`
2. Select `App registrations` and click `New application registration`
3. Enter `Lithnet Access Manager` or another suitable application name, and select `Accounts in this organizational directory only (This org only - Single tenant)` as the supported account type
4. Click `Register`
5. Take note of the `Application ID` value, this is our `client ID`
6. Save the settings
7. Take note of the Directory/Tenant ID from the main application page
8. From the `Certificates and secrets` page, click `new client secret`, give your secret a name, and then take note of the value provided.

If you want to enable user authentication via OIDC, then you'll also need to complete the following steps
1. From the left-hand menu, click `Manage` then `Authentication`. Click `Add a platform`.
2. Select `Web` as the platform type
3. In the `redirect URI` field enter the base URL where your Access Manager web app is hosted followed by `/auth` (e.g. `https://accessmanager.lithnet.local/auth`)
4. Set the `front-channel logout URL` to be the same as your base URL, with `/auth/logout` appended to it. (e.g. `https://accessmanager.lithnet.local/auth/logout`)
5. Click `Configure`

# Step 2: Grant directory permissions

1. From the `API permissions` page, click `Add permission` and grant the following API permissions, relevant to your scenario
2. Ensure that you have selected `Grant admin consent` for each item.
   
### User authentication using OpenID Connect

   | Permission | Require scenarios | Description |
   | --- | --- | --- |
   | Organization.Read.All | - All scenarios | Allows Access Manager to read basic tenant information such as the tenant name and tenant ID |
   | User.Read | Allows Access Manager to read information about users in the tenant when they log in |

### Accessing LAPS passwords stored in Entra

   | Permission | Require scenarios | Description |
   | --- | --- | --- |
   | Organization.Read.All | Allows Access Manager to read basic tenant information such as the tenant name and tenant ID |
   | Device.Read.All | Allows Access Manager to read information about devices in the tenant |
   | Group.Read.All | Allows Access Manager to read information about groups and their members |
   | AdministrativeUnit.Read.All | Allows Access Manager to read information about administrative units in the tenant |
   | DeviceLocalCredential.Read.All | Allows Access Manager to read LAPS passwords stored in the Entra directory, when using the Windows LAPS agent. Not required if using the Access Manager Agent to manage LAPS passwords |

### Deploying the Access Manager Agent to Entra-joined devices

   | Permission | Require scenarios | Description |
   | --- | --- | --- |
   | Organization.Read.All |Allows Access Manager to read basic tenant information such as the tenant name and tenant ID |
   | Device.Read.All | Allows Access Manager to read information about devices in the tenant |
   | Group.Read.All  | Allows Access Manager to read information about groups and their members |
   | AdministrativeUnit.Read.All | Allows Access Manager to read information about administrative units in the tenant |

