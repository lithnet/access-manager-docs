# Setting up Lithnet Access Manager Agent RapidLAPS  policies

This guide will walk you through configuring RapidLAPS policies in an Access Manager Agent policy.

*RapidLAPS* integrates into the Windows lock screen and UAC prompts, allowing you to speed up the LAPS process wherever you use local admin accounts. With *RapidLAPS*, using just a QR code, or PIN, you can remotely authorize and log into any LAPS-enabled computer, without ever having to type a long and complicated password.

This feature works whether you are using Windows LAPS, legacy LAPS, or the Access Manager agent to manage your LAPS passwords.

> Note: RapidLAPS policies can only be configured for Windows agents.

![](../../../images/ui-page-access-manager-agent-agent-policies-windows-policies-edit-rapidlaps.png)

## Step 1. Configure where RapidLAPS should be enabled

First, select which areas in Windows you wish to enable RapidLAPS:

### Enable RapidLAPS for logins

When configured, this setting will add a "Login with Lithnet RapidLAPS" tile to the Windows lock screen, allowing login to the local administrator account via Access Manager.

### Enable RapidLAPS for elevation

When configured, this setting will add an "Elevate with Lithnet RapidLAPS" tile to the Windows UAC prompt, allowing elevation of applications, installers, and system actions with the local administrator account via Access Manager.

## Step 2. Configure user prompts

Optionally, you can present users with a series of "prompts" whenever they login or elevate with RapidLAPS. Responses to these prompts are delivered to the server if a login or elevation is attempted, and are presented to the user authorizing the request in the Access Manager web app (as well as being stored in the audit log).

![](../../../images/ui-page-access-manager-agent-agent-policies-windows-policies-edit-rapidlaps-edit-ui-prompt.png)

The following options are configurable for user prompts:
* __Usage scenarios__: Configure whether the prompt is shown with RapidLAPS requests at either the *login screen* or during *elevation*.
* __Data type__: The type of prompt
  * *Text*: A simple text-box
  * *Multiline text*: A text box with multiple lines for long-form responses
  * *Drop-down list*: A drop down box, where a user can select an option from a list
  * *Checkbox*: A simple checkbox
  * *Label*: A piece of text that will appear in the prompt window (e.g., for providing organization-specific guidance)
* __Helper text__: An optional message presented alongside the prompt
* __Required__: Whether the specific prompt is required
* `Text` and `Multiline text`-specific fields
    * __Minimum length__: The minimum length of the text input; set to "0" to disable length requirements
    * __Validation regex__: An optional regular expression for validating text
    * __Validation failure message__: An optional message to present to users when the validation requirements are not met
* `Drop-down list`-specific fields
    * __List options__: A list of options a user can select in the drop down

## Step 3. Create computer authorization rules for RapidLAPS

Once the policy is configured, you can now configure individual users and groups who can approve RapidLAPS logins or elevations using the AMS configuration tool.

From the `Authorization rules/Computers` page, select `Add...` to create a new authorization rule. Select the container containing the computers you wish to allow RapidLAPS access to, and provide a friendly description for this rule. This will appear in audit logs if a user is approves or denies a request.

Select `Edit Permissions...` to open the ACL editor. Assign the appropriate users and groups permission to allow RapidLAPS login and/or elevation approval access.

![!](../../../images/ui-page-authz-editsecurity-rapidlaps.png)

If you'd like to be notified when someone requests RapidLAPS login or elevation, select the notification channels you'd like to send to for success and failure events.

For more information on RapidLAPS, see the [RapidLAPS help page](../../../help-and-support/advanced-help-topics/rapidlaps.md).