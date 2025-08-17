# Enabling Secure Token Support for macOS

{% hint style="info" %}
This feature is currently in preview. 
{% endhint %}

This document explains how to configure Lithnet Access Manager to work with macOS accounts that have secure token enabled.

{% hint style="info" %}
Secure token support requires Access Manager Agent version 3.0.1500 or later. Older agent versions will detect secure token and report an error that they are unable to change the password.
{% endhint %}

## Overview of Secure Token

Secure token is a macOS security feature introduced in macOS High Sierra (10.13). It is an encryption key protected by the user's password that allows them access to perform security-sensitive operations such as enabling FileVault, approving operating system updates and system and kernel extensions.

As this encryption key is protected by the user's password, this fundamentally changes how password management works for the account.

The most important difference is that **passwords cannot be reset directly** when secure token is enabled - they can only be **changed** using the current password. This means that any password modification requires knowledge of the existing password first, unlike accounts without secure token where passwords can be reset directly without knowing the current password. 

On every Mac system, the first user account created automatically receives secure token. Additional users can only be granted secure token by an existing user who already has it, or through certain Mobile Device Management (MDM) solutions that have been configured with the appropriate privileges. This makes secure token a controlled privilege that must be explicitly granted.

You can verify if an account has secure token enabled using the native macOS command:

```bash
sudo sysadminctl -secureTokenStatus username
```

This will return either "ENABLED" or "DISABLED" for the specified user.

## Secure Token Handling in Access Manager

Secure token support was added to Access Manager in agent version 3.0.1500. Prior versions do not support secure token and will report an error when attempting to manage accounts that have it enabled. Agent version 3.0.1500 and later now support both secure token enabled and non-secure token accounts.

### Accounts Without Secure Token

For accounts without secure token enabled, Access Manager continues to operate exactly as it did in previous versions. It **resets** the password directly using the `dscl` command without requiring knowledge of the current password. This allows Access Manager to change the password immediately without any prior setup or configuration.

However, there is one important change in version 3.0.1500 and later: Access Manager now encrypts and stores the current password for all accounts after each password change. This means that if secure token is enabled for an account at a later date, Access Manager can immediately switch to changing the password instead of resetting it, without requiring any additional configuration.

### Accounts With Secure Token Enabled

For accounts with secure token enabled, Access Manager uses the new functionality added in version 3.0.1500 to handle macOS security restrictions. It **changes** the password using `dscl -passwd` which requires the current password to be provided. Access Manager leverages the encrypted copy of the current password that it stores locally after each password change. When secure token is detected, the agent automatically switches from password reset mode to password change mode. If secure token becomes disabled for an account, Access Manager will automatically fall back to password reset mode.

## How to Set Up Secure Token Support

### Enable Secure Token for Existing Access Manager Account

This process allows you to enable secure token for accounts already managed by Access Manager.

{% hint style="info" %}
Access Manager is unable to programmatically enable secure token, as only a user with a secure token can enable secure token for another user. You'll need to determine a way to enable secure token for the managed admin account using an external process such as an MDM tool or a script-based solution. 
{% endhint %}


**Steps:**

1. **Deploy agent version 3.0.1500 or later** to the macOS computer

2. **Ensure the agent has an encrypted copy of the current password:**
   - Wait for the next password change interval based on your Access Manager policy, OR
   - Manually expire the passwords on the Access Manager server for the target computers to trigger an immediate password change

3. **Validate that Access Manager has the password stored:**
   ```bash
   sudo Lithnet.AccessManager.Agent secure-token-support get
   ```
   The account should appear in the list if the password is stored.

4. **After confirming that Access Manager has the current password stored**, enable secure token for the account. This operation must be performed by a user who already has secure token:
   
   ```bash
   sudo sysadminctl -secureTokenOn <accountName> -password <password> -adminUser <adminuser> -adminPassword <adminpassword>
   ```
   
   Replace `<accountName>` and `<password>` with the username and password of the Access Manager-managed admin account, and `<adminuser>` and `<adminpassword>` with the credentials of a user who has an existing secure token.
   
   For enhanced security, you can use `-` instead of providing passwords directly to be prompted for them:
   ```bash
   sudo sysadminctl -secureTokenOn <accountName> -password - -adminUser <adminuser> -adminPassword -
   ```

5. **Verify secure token is enabled:**
   ```bash
   sudo sysadminctl -secureTokenStatus username
   ```

**Note:** If you need to reset the account's password manually to use another method of enabling secure token with a known password, you can skip steps 2 and 3 above. Instead, run the `set` command after enabling secure token to provide Access Manager with the updated password:

```bash
sudo Lithnet.AccessManager.Agent secure-token-support set --username adminuser --password current-password
```

The agent will now automatically handle password changes for the secure token account using the stored encrypted password.

## Managing Secure Token Support

### Viewing Configured Accounts

To see which accounts are currently configured for secure token support:

```bash
sudo Lithnet.AccessManager.Agent secure-token-support get
```

### Clearing Stored Credentials

To remove secure token support for a specific account:

```bash
sudo Lithnet.AccessManager.Agent secure-token-support clear --username adminuser
```

To remove secure token support for all accounts:

```bash
sudo Lithnet.AccessManager.Agent secure-token-support clear
```

### Updating Stored Passwords

If the stored password becomes out of sync with the actual account password, you can update it:

```bash
sudo Lithnet.AccessManager.Agent secure-token-support set --username adminuser --password current-password
```

## Troubleshooting

### Password Out of Sync Error

**Problem:** Access Manager reports it cannot change the password for a secure token account.

**Cause:** The stored password is out of sync with the actual account password.

**Solution:** 
1. Determine the current password for the account
2. Update the stored password using:
   ```bash
   sudo Lithnet.AccessManager.Agent secure-token-support set --username adminuser --password actual-current-password
   ```

### Agent Version Too Old

**Problem:** Error messages about being unable to change passwords for secure token accounts.

**Cause:** Agent version is older than 3.0.1500.

**Solution:** Upgrade the Access Manager Agent to version 3.0.1500 or later.
