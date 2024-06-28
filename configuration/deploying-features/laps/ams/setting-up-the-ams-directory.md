# Preparing the AMS directory

![](../../../../images/badge-enterprise-edition-rocket.svg) Managing more than 100 devices in the Access Manager directory is an [Enterprise edition feature](../../../../access-manager-editions.md)

The Lithnet Access Manager Agent (AMA) supports managing local administrator accounts and passwords on Windows, macOS and Linux devices, no matter how those devices are configured.

When using the Lithnet Access Manager Agent (AMA) on devices that are not joined to an Active Directory (non-Windows devices, Azure AD devices, and standalone Windows devices), the AMA stores passwords in the Access Manager Directory.

> Note: The Lithnet Access Manager Agent can co-exist with Windows LAPS, in the instance where you wish to use a feature such as *RapidLAPS* while retaining your existing Windows LAPS configuraiton.

The agent will check-in with the AMS server at regular intervals, updating it's policy and checking if any password change is required.

If as password change is required, the agent will rotate the password of a local administrator account of your choosing with a randomly-generated password or passphrase, encrypts the password, and securely submits the password to the AMS server to be stored in it's internal database.


The following guide outlines the steps required to enable the AMS directory service.

## Step 1: Enable API support

From the `Host configuration` page, tick `Enable agents to communicate with this host`, and specify the host name clients will use to connect to the server. This must match the DNS name in the active TLS/SSL certificate, or clients will be unable to connect.

![](../../../../images/ui-page-host-configuration.png)

{% hint style="info" %}
If you wish to allow agents to register with their Active Directory identity, you will need to configure a service prinicipal name (SPN) on the service account used by the Access Manager Service.

If this SPN is not set, the following warning will appear in the `Service account` section of the `Host configuration` page:
![](../../../../images/spn-warning.png)
{% endhint %}


## Step 2: Enable device registration modes

From the `Access Manager Agent/Agent registration` page, select mechanisms by which devices will register with the AMS server:
- Windows authentication can be used to automatically register Active Directory-joined devices with AMS.
- Microsoft Entra authentication can be used to register Entra-joined devices with AMS.
- Registration keys can be configured to register all standalone devices with AMS.

![](../../../../images/ui-page-access-manager-agent-agent-registration.png)

If you do not plan on using Entra device registration, then the setup process is complete.

## Step 3: Configure Azure Active Directory tenant details

If you enable Microsoft Entra device registration, you must register your Entra ID tenant details, and grant permission for the service to read information from your AAD.

If you are using Entra ID authentication for AMS, you can reuse the app registration created for authentication. Skip to the `Granting directory permissions` section below.

If you are not using Entra ID for authentication, or you'd like to create a separate application for the directory access, then follow these steps to create a new application in Entra ID.

### Configure a new application in Entra ID

1. Log into portal.azure.com with administrative credentials, select `More services` and select `Microsoft Entra ID`
2. Select `App registrations` and click `New application registration`
3. Enter `Lithnet Access Manager` or another suitable application name, and select `Accounts in this organizational directory only (Lithnet only - Single tenant)` as the supported account type
4. Leave the `redirect URI` field blank
5. Click `Register`
6. Take note of the `Application ID` value, this is our client ID
7. Save the settings
8. Take note of the Directory/Tenant ID from the main application page
9. From the `Certificates and secrets` page, click `new client secret`, give your secret a name, and then take note of the value provided.

### Granting directory permissions

1. Log into portal.azure.com with administrative credentials, select `More services` and select `Microsoft Entra ID`
2. Select `App registrations` and select your Application registration for Lithnet Access Manager.
3. From the `API permissions` page, click `Add permission` and grant the following API permissions
   * Device.Read.All
   * Group.Read.All
   * Organization.Read.All
   * User.Read
4. Ensure that you have selected `Grant admin consent` for each item.

### Configure the service account details in Access Manager

1. Open the Lithnet Access Manager Service Configuration Tool
2. Select the `Directory configuration/Microsoft Entra` page
3. Press the `Add...` button to add a new tenant configuration
4. Add the client ID, secret, and directory/tenant ID in the fields provided
5. Save the tenant configuration

{% hint style="info" %}
You may need to wait a minute or two for the secret and delegation to become active
{% endhint %}

Access Manager is now configured to support Azure AD joined and registered devices.
