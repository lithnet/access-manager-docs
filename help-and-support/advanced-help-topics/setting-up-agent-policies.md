# Setting up Lithnet Access Manager Agent policies

This guide will walk you through the steps to configure policies for the Lithnet Access Manager Agent.

Agent policies are used to configure features such as *password management*, *RapidLAPS*, and *BitLocker recovery key backup*.

The agent will periodically "check-in" with the Access Manager Server to retrieve the appropriate policy.

## Types of policies

Agent policies are divided into three categories, based on the target operating system: _Windows_, _macOS_ and _Linux_.

Each operating system has a __default__ policy, and a set of __custom__ policies.

You can create custom Access Manager Agent policies that are targeted at specific computers, groups and containers - from Active Directory, Microsoft Entra, or AMS.

## Policy precedence
Policies are processed in the order they appear in the custom agent policy list. The first policy that matches a given computer is the policy that will be used.

You should ensure that the most specific policies (eg policies that target individual computers and groups) are located at the top of the list.

If no matching policy can be found, the default agent policy will be used.

## Default agent policy
The default agent policy is the 'fallback' policy that will be used when a computer does not match any of the custom policies configured.

It should contain settings that are applicable as a default base across your environment. 

If all computers should have the same policy settings, then there is no need to configure custom policies at all. 

## Creating a new policy

If you need to vary policy settings between devices, then you'll need to create a custom policy, and target it to those devices.

### Step 1. Navigate to an OS-specific policy page

To create an agent policy, first select the operating system you wish to configure policy for in the sidebar under `Access Manager Agent/Agent policies`:

![](../../images/agent-policy-sidebar.png)

### Step 2. Create a new custom agent policy

Click the `Create new...` button at the bottom of the custom agent policy list.

### Step 3. Configure general policy settings

![](../../images/agent-policy-edit-generic.png)

On the first page of the policy editor - configure a memorable name and a description for your custom policy.

Next, configure the "Agent check-in interval". This setting determines how frequently the agent should attempt to check-in to the server - in minutes. When an agent checks in, it will receive policy updates, reset local administrator account passwords (if required), and backup disk encryption keys (if required). The default value is to check-in every to 60 minutes.

Next, configure the "targets" for your custom policy. Policies can be targeted at specific computers, groups and containers - from Active Directory, Microsoft Entra, or AMS.

To add a new target to a policy, simply click `Add...` at the bottom of the target list, and follow the prompts to select your target computer, group, or container.

### Step 4. Configure your policy settings

Next, you can configure agent settings by selecting from the tabs on the left-hand side of the policy editor.

For more details, visit the appropriate guide for setting up each feature
* [Setting up Lithnet LAPS](../../configuration/deploying-features/laps/setting-up-lithnet-laps.md)
* [Setting up RapidLAPS (Windows only)](../../configuration/deploying-features/rapidlaps/setting-up-rapid-laps.md)
* [Setting up BitLocker backup (Windows only)](../../configuration/deploying-features/fve-backup/setting-up-bitlocker-ams.md)

### Step 5. Save the policy

To save the custom policy and make it available for clients, simply click the `Save` button in the bottom right-hand corner of the policy editor.

## More information

For more information on the different settings configurable in agent policies, see the corresponding help page:
* [Windows agent policies page](../app-pages/access-manager-agent-policies-windows-page.md)
* [macOS agent policies page](../app-pages/access-manager-agent-policies-macos-page.md)
* [Linux agent policies page](../app-pages/access-manager-agent-policies-linux-page.md)
* [Legacy (v2) agent policies page](../app-pages/access-manager-agent-policies-amsv2-page.md)