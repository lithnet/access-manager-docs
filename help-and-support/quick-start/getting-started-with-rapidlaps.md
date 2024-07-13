# Getting started with RapidLAPS

RapidLAPS is Lithnet Access Manager's passwordless login system for LAPS accounts.

This quick-start guide will provide you with all the information you need to get up-and-running with using Lithnet Access Manager to enable RapidLAPS login to your windows devices.

### Step 1: Install Lithnet Access Manager Server

Now you can proceed with installing Access Manager itself. Our [detailed setup guide](/installation/installing-the-access-manager-server/installing-the-access-manager-service.md) will walk you through the process.

If you just want to set up a quick test environment, you can use a single server deployment, with the built-in SQL Express engine, to simplify the deployment.

### Step 2: Select and configure a LAPS agent

Using RapidLAPS first requires that the computers you are deploying to have a LAPS agent installed and running.

This can be the legacy Microsoft LAPS agent, the new built-in Windows LAPS agent, or you can use the Access Manager agent to manage your LAPS passwords.

While RapidLAPS requires that you deploy the Access Manager agent to your devices, you don't need to use it to manage the LAPS password itself.

If you have Microsoft LAPS up and running already, then skip over to the next step. Otherwise, following one of these guides to configure the LAPS agent of your choosing
* [Getting started with Windows LAPS](getting-started-with-windows-laps.md)
* [Setting up Lithnet LAPS](../../configuration/deploying-features/laps/setting-up-lithnet-laps.md)

### Step 3: Configure Access Manager to read LAPS passwords

Once you've deployed LAPS, you'll need to configure the Access Manager service to be able to read those LAPS passwords using one of the following guides.

* [Setting up Microsoft LAPS for Active Directory](../../configuration/deploying-features/laps/setting-up-microsoft-laps.md)
* [Setting up Microsoft LAPS for Microsoft Entra](../../configuration/deploying-features/laps/setting-up-microsoft-laps-for-aad.md)
* [Setting up Lithnet LAPS](../../configuration/deploying-features/laps/setting-up-lithnet-laps.md)

### Step 4: Test LAPS Access

Before configuring RapidLAPS, make sure you can access the LAPS password from the Access Manager web app first. If you're unable to retrieve the LAPS password, RapidLAPS wont be able to either, so it's imperative to ensure that you test with web-based access to LAPS passwords first.

### Step 5: Configure RapidLAPS

Once you've validated that Access Manager can read your LAPS passwords, you can proceed with the final stage of configuring RapidLAPS

* [Setting up RapidLAPS](../../configuration/deploying-features/rapidlaps/setting-up-rapid-laps.md)

### Step 6: Test RapidLAPS access

On a machine where RapidLAPS is configured, logout, and you should be presented with a new tile on the login screen for "Login with RapidLAPS".

Check out our [troubleshooting guide](../troubleshooting.md) for more help.
