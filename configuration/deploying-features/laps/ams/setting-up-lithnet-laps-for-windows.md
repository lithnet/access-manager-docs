# Setting up Lithnet LAPS for domain-joined Windows devices

This guide will walk you through the steps to configure the Access Manager service, and the Access Manager agent to support managing the local admin password on Windows machines that are joined to Active Directory.

## Step 1: Set up the AMS directory

The Lithnet Access Manager agent can use the Access Manager directory to store passwords for standalone Windows devices. Follow the steps in the [AMS directory setup guide](setting-up-the-ams-directory.md).

> Note: if Windows LAPS or legacy LAPS is in use on a machine, the Access Manager agent will *not* manage local administrator passwords. This behaviour allows you to utilize features such as RapidLAPS without having to migrate fully to AMS-managed local administrator passwords.

## Step 2: Configure Lithnet LAPS for the Access Manager directory

Next, configure [Lithnet LAPS for the AMS directory](configuring-lithnet-laps-for-the-ams-directory.md). This process will configure the encryption certificate for the service, and set up  agent policies as required.

## Step 3: Create a registration key

From the `Access Manager Agent/Agent registration` page, ensure that the `Allow agents to register using Windows (negotiate) authentication` checkbox is ticked.

If you have not already done so, ensure that you have configured an appropriate service principal name (SPN) for the Access Manager Service in Active Directory __TODO__

## Step 4: Install the Access Manager Agent

Following [agent installation guide](../../../../installation/installing-the-access-manager-agent/installing-the-access-manager-agent-windows.md), selecting the Access Manager password storage mode, and Active Directory authentication when prompted.

The installation guides provide command lines for silently installing the package, which can be used with automated deployment tools such as SCCM. Configuring these deployment tools is out of scope for this guide.

## Step 5: Validate agent installation

From the `Access Manager Agent/Devices` page, ensure that the devices you installed the agent have appeared in the device list. If you configured your registration key to require manual approval, you must approve the devices before they can be accessed.ß

## Step 6: Assign access

Once the agent is deployed, and the policy configured, you can now configure access to individual users and groups using the AMS configuration tool.

From the `Authorization rules/Computers` page, select `Add...` to create a new target. Select either the group or computer you want to grant access to. Access Manager provides some built-in groups, but you can create your own from the [groups page](../../../../help-and-support/app-pages/access-manager-directory-groups-page.md).

Select `Edit Permissions...` to open the ACL editor. Assign the appropriate users and groups permission to read the local admin password.

![](../../../../images/ui-page-authz-editsecurity-laps-only.png)

You can optionally choose to expire the local admin password a period of time after it has been accessed. This will cause the Access Manager Agent to generate a new password _after_ its next check-in time.

If you'd like to be notified when someone accesses a LAPS password, select the notification channels you'd like to send to for success and failure events.

## Step 7: Validate access

Log in to the Access Manager web app as an authorized user, and request access to the password for a computer. If you have performed the steps correctly, you should be able to see the machine's root password.
