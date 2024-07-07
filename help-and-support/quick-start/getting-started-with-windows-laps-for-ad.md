# Getting started with Windows LAPS for Active Directory

This quick-start guide will provide you with all the information you need to get up-and-running with using Lithnet Access Manager to access LAPS passwords created by the new Windows LAPS agent.

### Step 1: Prepare the Active Directory for Windows LAPS

Windows LAPS requires some new schema attributes and permissions to be delegated. Follow Microsoft's [setup guide](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-scenarios-windows-server-active-directory) for preparing your Active Directory to work with Microsoft LAPS.

### Step 2: Enable and configure Windows LAPS

Make sure your test machines have installed the April 2023 Windows updates, which include the new LAPS capability.

Configure your LAPS clients via [group policy](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-management-policy-settings)

### Step 3: Test LAPS Access

Before configuring Access Manager, it's a good idea to make sure that LAPS is working natively first. You can use the built-in [PowerShell](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-scenarios-windows-server-active-directory#retrieve-a-password-from-windows-server-active-directory) modules to make sure you can access the LAPS passwords. Once you are confident that it is all working, you can move onto the next step of installing Access Manager.

### Step 4: Install Lithnet Access Manager Server

Now you can proceed with installing Access Manager itself. Our [detailed setup guide](/installation/installing-the-access-manager-server/installing-the-access-manager-service.md) will walk you through the process.

If you just want to set up a quick test environment, you can use a single server deployment, with the built-in SQL Express engine, to simplify the deployment.

### Step 5: Configure Access Manager to read LAPS passwords

Once Access Manager is installed, you need to grant it the permissions it needs to read passwords from the directory, and assign access to your users.

Follow the steps in the [configuration guide for Microsoft LAPS](../../configuration/deploying-features/laps/setting-up-microsoft-laps.md) to correctly delegate and assign user permissions.

### Step 6: Test user access

Visit the Access Manager web app in the browser and request the LAPS password for your test computer. If you have configured the app correctly, you should be presented with the LAPS password for the machine.

Check out our [troubleshooting guide](../troubleshooting.md) for more help.
