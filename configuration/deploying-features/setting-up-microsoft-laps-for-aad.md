# Setting up Microsoft LAPS for Azure Active Directory

Lithnet Access Manager provides a convenient web-based interface for accessing local admin passwords that have been stored in Azure AD by Windows LAPS.

This guide assumes that you have the Windows LAPS agent deployed and configured appropriately. Test access to the LAPS passwords using the Azure portal first to make sure it is configured correctly.

This guide focuses on setting up support for Microsoft LAPS passwords stored in Azure Active Directory. See our other guide for passwords stored in [Active Directory](setting-up-microsoft-laps.md).

## Step 1: Configure a new application in Azure AD
If you are using Azure AD authentication for AMS, you can reuse the app registration created for authentication. Skip to Step 2.

If you are not using Azure AD for authentication, or you'd like to create a separate application for the directory access, then follow these steps to create a new application in Azure AD.

1. Log into portal.azure.com with administrative credentials, select `All services` and select `Azure Active Directory`
2. Select `App registrations` and click `New application registration`
3. Enter `Lithnet Access Manager` or another suitable application name, and select `Accounts in this organizational directory only (Lithnet only - Single tenant)` as the supported account type
4. Leave the `redirect URI` field blank
5. Click `Register`
6. Take note of the `Application ID` value, this is our client ID
7. Save the settings
8. Take note of the Directory/Tenant ID from the main application page
9. From the `Certificates and secrets` page, click `new client secret`, give your secret a name, and then take note of the value provided.

## Step 2: Granting directory permissions

1. Log into portal.azure.com with administrative credentials, select `All services` and select `Azure Active Directory`
2. Select `App registrations` and select your Application registration for Lithnet Access Manager.
3. From the `API permissions` page, click `Add permission` and grant the following API permissions
   * Device.Read.All
   * Group.Read.All
   * Organization.Read.All
   * User.Read
   * DeviceLocalCredential.Read.All

4. Ensure that you have selected `Grant admin consent` for each item.

## Step 3: Configure the service account details in Access Manager

1. Open the Lithnet Access Manager Service Configuration Tool
2. Select the `Directory configuration/Azure Active Directory` page
3. Press the `Add...` button to add a new tenant configuration
4. Add the client ID, secret, and directory/tenant ID in the fields provided
5. Save the tenant configuration

{% hint style="info" %}
You may need to wait a minute or two for the secret and delegation to become active
{% endhint %}

## Step 4: Assign access

The final step is to create an authorization rule, granting permission for your selected users and groups to access the LAPS passwords for the specified computers.

From the `Authorization rules/Computers` page, select `Add...` to create a new rule. Select the Azure AD tenant, device group, or computer you want to assign access to, and provide a friendly description for this rule. This will appear in audit logs if a user is granted access.

Expand the `Access control` section and select `Edit Permissions...` to open the ACL editor.

![!](../../images/ui-page-authz-editsecurity-laps-only.png)

{% hint style="info" %}
When a computer is using Microsoft's Windows LAPS agent, and it is configured to store its password in Azure AD, then password rotation is not possible. Azure AD does not provide an API that AMS can use to indicate to the machine that the password should be rotated. 

You can however use the built-in [PostAuthenticationActions and PostAuthenticationResetDelay policy settings](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-management-policy-settings#postauthenticationresetdelay) to trigger the password change after logon.
{% endhint %}

If you'd like to be notified when someone accesses a LAPS password, select the notification channels you'd like to send to for success and failure events.
