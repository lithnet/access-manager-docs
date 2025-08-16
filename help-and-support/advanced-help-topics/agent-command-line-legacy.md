# Lithnet Access Manager Agent Command Line Reference (Legacy)

This document provides a reference for command line options for the Lithnet Access Manager Agent versions prior to 3.0.1480.

{% hint style="info" %}
This documentation applies to agent versions less than 3.0.1480. For agent versions 3.0.1480 and later, please refer to the [updated command line reference](agent-command-line.md) which uses a new structured command format.
{% endhint %}

## Global Options

These options apply to all platforms:

| Option | Description |
|--------|-------------|
| `--help` | Shows help information for the command |
| `--version` | Shows version information |

## Interactive Setup

```
Lithnet.AccessManager.Agent --setup
```

Perform setup using interactive setup wizard. This command will:
1. Prompt for server address
2. Prompt for registration mode
3. Collect additional information based on the selected mode
4. Apply the configuration and restart the service

## Non-Interactive Setup

### Active Directory (Negotiate) Authentication

```
Lithnet.AccessManager.Agent --server <servername> --registration-mode iwa
```

Perform setup without user interaction, using Active Directory (Negotiate) authentication.

| Option | Description |
|--------|-------------|
| `--server <servername>` | Set the hostname of the AMS server |
| `--registration-mode iwa` | Use Negotiate authentication to register the agent |

### Microsoft Entra Authentication (Windows Only)

```
Lithnet.AccessManager.Agent --server <servername> --registration-mode entra
```

Perform setup without user interaction, using Microsoft Entra as the authentication provider.

| Option | Description |
|--------|-------------|
| `--server <servername>` | Set the hostname of the AMS server |
| `--registration-mode entra` | Use Microsoft Entra authentication to register the agent |

> **Note:** The `entra` registration mode is only available on Windows platforms.

### Registration Key Authentication

```
Lithnet.AccessManager.Agent --server <servername> --registration-mode key --registration-key <key>
```

Perform setup without user interaction, using a registration key for authentication.

| Option | Description |
|--------|-------------|
| `--server <servername>` | Set the hostname of the AMS server |
| `--registration-mode key` | Use a key to register the agent |
| `--registration-key <key>` | Set the registration key |

## Agent State Control

Control the agent state:

```
Lithnet.AccessManager.Agent --disable
Lithnet.AccessManager.Agent --enable
```

| Option | Description |
|--------|-------------|
| `--disable` | Disable the agent |
| `--enable` | Enable the agent |

## Agent Reset

Reset the agent. This deletes all settings and authentication certificates:

```
Lithnet.AccessManager.Agent --reset
Lithnet.AccessManager.Agent --reset --force
Lithnet.AccessManager.Agent --reset --keep-cert
```

| Option | Description |
|--------|-------------|
| `--reset` | Reset the agent |
| `--reset --force` | Reset the agent without prompting for confirmation |
| `--reset --keep-cert` | Reset the agent but keeps the agent's auth certificate |

## Administration Requirements

Many commands require administrator rights:
- Windows: Run Command Prompt or PowerShell as Administrator
- macOS/Linux: Use sudo or run as root

## Examples of Common Workflows

### Initial Setup with Active Directory
```
Lithnet.AccessManager.Agent --server ams.example.com --registration-mode iwa
```

### Initial Setup with Registration Key
```
Lithnet.AccessManager.Agent --server ams.example.com --registration-mode key --registration-key YOUR-KEY-HERE
```

### Disable Agent
```
Lithnet.AccessManager.Agent --disable
```

### Reset Agent
```
Lithnet.AccessManager.Agent --reset --force
```

## Troubleshooting

If you encounter issues:

1. Ensure you're running with administrator rights
2. Check the agent logs
3. For agent versions 3.0.1480 and later, refer to the [updated command line reference](agent-command-line.md)
4. Try resetting the agent with `--reset --force`

For additional help, consult the full Lithnet Access Manager documentation.
