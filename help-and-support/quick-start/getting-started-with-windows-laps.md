# Getting started with Windows LAPS and Lithnet Access Manager

Microsoft [has announced](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/by-popular-demand-windows-laps-available-now/ba-p/3788747) that a new version of Windows LAPS has been released via Windows Update to Windows 10, 11, Windows Server 2019 and above. This brings LAPS capability to all supported operating systems without needing any additional installation.

Windows LAPS replaces the 'legacy' LAPS that required a separate installation, and is now built into the operating system itself. It has received major new features including support for encrypting LAPS passwords, and storing a history of LAPS passwords.

The great news is that Lithnet Access Manager works with Windows LAPS out of the box!

Lithnet Access Manager provides a simple web-based and mobile-friendly interface for accessing local admin passwords. There’s no need to install custom software, or have access to AD administrative tools or PowerShell to access LAPS passwords.

It's MFA-ready with native support for Azure AD, Okta, ADFS, and even smart cards via OpenID Connect. It has easy to use, yet highly customizable auditing capability coupled with a granular and extensible permission model.

When combined, Windows LAPS and Lithnet Access Manager make the perfect pair ❤

![](../../.gitbook/assets/web-request-laps.gif)

In this guide, we'll show you how to get up and running by configuring Windows LAPS, and then accessing those passwords with Lithnet Access Manager.

## Step 1: Prepare the Active Directory for Windows LAPS

Windows LAPS requires some new schema attributes and permissions to be delegated. Follow Microsoft's [setup guide](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-scenarios-windows-server-active-directory) for preparing your Active Directory to work with Microsoft LAPS.

## Step 2: Enable and configure Windows LAPS

Make sure your test machines have installed the April 2023 Windows updates, which include the new LAPS capability.

Configure your LAPS clients via [group policy](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-management-policy-settings)

## Step 3: Test LAPS Access

Before configuring Access Manager, it's a good idea to make sure that LAPS is working natively first. You can use the built-in [PowerShell](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-scenarios-windows-server-active-directory#retrieve-a-password-from-windows-server-active-directory) modules to make sure you can access the LAPS passwords. Once you are confident that it is all working, you can move onto the next step of installing Access Manager.

## Step 4: Install Lithnet Access Manager Server

Now you can proceed with installing Access Manager itself. Our [detailed setup guide](https://docs.lithnet.io/ams/installation/installing-the-access-manager-server/installing-the-access-manager-service) will walk you through the process.

If you just want to set up a quick test environment, you can use a single server deployment, with the built-in SQL Express engine, to simplify the deployment.

## Step 5: Configure Access Manager to read LAPS passwords

Once Access Manager is installed, you need to grant it the permissions it needs to read passwords from the directory, and assign access to your users.

Follow the steps in the [configuration guide for Microsoft LAPS](https://docs.lithnet.io/ams/configuration/deploying-features/setting-up-microsoft-laps) to correctly delegate and assign user permissions.

## Step 6: Test user access

Visit the Access Manager web app in the browser and request the LAPS password for your test computer. If you have configured the app correctly, you should be presented with the LAPS password for the machine.

Check out our [troubleshooting guide](../troubleshooting.md) for more help.
