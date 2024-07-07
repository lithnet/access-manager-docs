# Setting up Microsoft LAPS for Entra

Lithnet Access Manager provides a convenient web-based interface for accessing local admin passwords that have been stored in Entra ID by Windows LAPS.

This guide assumes that you have the Windows LAPS agent deployed and configured appropriately. Test access to the LAPS passwords using the Entra portal first to make sure it is configured correctly.

This guide focuses on setting up support for Windows LAPS passwords stored in Microsoft Entra. See our other guide for passwords stored in [Active Directory](setting-up-microsoft-laps.md).

## Step 1: Configure a new application in Entra ID

Follow the steps in [Creating an Entra app for Access Manager](../../../help-and-support/advanced-help-topics/creating-an-entra-app.md) to create the app registration for Access Manager. Take note of the tenant ID, client ID and secret created here as they will be used in the next step.

Ensure that the appropriate API permissions have been granted for the `Accessing LAPS passwords stored in Entra` scenario.

## Step 2: Configure the service account details in Access Manager

1. Open the Lithnet Access Manager Service Configuration Tool
2. Select the `Directory configuration/Microsoft Entra` page
3. Press the `Add...` button to add a new tenant configuration
4. Add the client ID, secret, and directory/tenant ID in the fields provided
5. Save the tenant configuration

{% hint style="info" %}
You may need to wait a minute or two for the secret and delegation to become active
{% endhint %}

## Step 3: Assign access

The final step is to create an authorization rule, granting permission for your selected users and groups to access the LAPS passwords for the specified computers.

From the `Authorization rules/Computers` page, select `Add...` to create a new rule. Select the Entra ID tenant, device group, or computer you want to assign access to, and provide a friendly description for this rule. This will appear in audit logs if a user is granted access.

Expand the `Access control` section and select `Edit Permissions...` to open the ACL editor.

![!](../../../images/ui-page-authz-editsecurity-laps-only.png)

{% hint style="info" %}
When a computer is using Microsoft's Windows LAPS agent, and it is configured to store its password in Microsoft Entra, then forced password rotation by Access Manager is not possible. Entra ID does not provide an API that AMS can use to indicate to the machine that the password should be rotated. 

You can however use the built-in [PostAuthenticationActions and PostAuthenticationResetDelay policy settings](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-management-policy-settings#postauthenticationresetdelay) to trigger the password change after logon.
{% endhint %}

If you'd like to be notified when someone accesses a LAPS password, select the notification channels you'd like to send to for success and failure events.


## Step 4: Validate access
Log in to the Access Manager web app as an authorized user, and request access to the password for a computer. If you have performed the steps correctly, you should be able to see the machine's  password.

If passwords cannot be retrieved, double check that you have followed the steps in this article, and see the [troubleshooting guide](../../../help-and-support/troubleshooting.md) for how to find the Access Manager server logs to help understand and resolve the issue.