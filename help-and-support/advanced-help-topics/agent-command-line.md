# Lithnet Access Manager Agent Command Line Reference

This document provides a comprehensive reference to the command line interface (CLI) for the Lithnet Access Manager Agent. The agent supports different commands based on the operating system platform (Windows, macOS, or Linux).

{% hint style="info" %}
These command line options are available in agent versions 3.0.1500 and later. For agent versions less than 3.0.1500, please refer to the [legacy command line reference](agent-command-line-legacy.md)
{% endhint %}


## Global Options

These options apply to all platforms:

| Option | Description |
|--------|-------------|
| `--help` | Shows help information for the command |
| `--version` | Shows version information |

## Core Commands

### Service Management

Control the Access Manager Agent service:

```
Lithnet.AccessManager.Agent service <command>
```

Available commands:

| Command | Description |
|---------|-------------|
| `start` | Start the Access Manager Agent service |
| `stop` | Stop the Access Manager Agent service |
| `restart` | Restart the Access Manager Agent service |

**Examples:**
```
Lithnet.AccessManager.Agent service start
Lithnet.AccessManager.Agent service stop
Lithnet.AccessManager.Agent service restart
```

### Agent Management

Control the agent state:

```
Lithnet.AccessManager.Agent agent <command>
```

Available commands:

| Command | Description |
|---------|-------------|
| `enable` | Enable the agent |
| `disable` | Disable the agent (sets the agent to a disabled state that persists across reboots) |

**Examples:**
```
Lithnet.AccessManager.Agent agent enable
Lithnet.AccessManager.Agent agent disable
```

### Configuration

Configure the agent:

```
Lithnet.AccessManager.Agent config [options]
```

Available options:

| Option | Description |
|--------|-------------|
| `--server <server>` | Set the hostname of the AMS server |
| `--port <port>` | Set the HTTPS port for the AMS server (default is 443) |
| `--registration-mode <mode>` | Set the registration mode (`iwa`, `key`, or `entra` on Windows) |
| `--registration-key <key>` | Set the registration key (automatically sets mode to `key`) |

**Examples:**
```
Lithnet.AccessManager.Agent config --server ams.example.com --port 443
Lithnet.AccessManager.Agent config --registration-mode iwa
Lithnet.AccessManager.Agent config --registration-mode key --registration-key YOUR-KEY
```

> **Note:** The `entra` registration mode is only available on Windows platforms. Setting a `--registration-key` automatically sets the registration mode to `key`.

### Setup Command

Interactive setup wizard to configure the agent:

```
Lithnet.AccessManager.Agent setup
```

This command will:
1. Prompt for server address
2. Prompt for registration mode
3. Collect additional information based on the selected mode
4. Apply the configuration and restart the service

### Reset Command

Reset the agent configuration:

```
Lithnet.AccessManager.Agent reset [options]
```

Available options:

| Option | Description |
|--------|-------------|
| `--force` | Skip confirmation prompt |
| `--keep-cert` | Keep the authentication certificate during reset |

**Examples:**
```
Lithnet.AccessManager.Agent reset
Lithnet.AccessManager.Agent reset --force
Lithnet.AccessManager.Agent reset --keep-cert
```

### Show Command

Display agent information:

```
Lithnet.AccessManager.Agent show <command>
```

Available commands:

| Command | Description |
|---------|-------------|
| `config` | Display the current configuration settings |
| `state` | Display current agent state information |

**Examples:**
```
Lithnet.AccessManager.Agent show config
Lithnet.AccessManager.Agent show state
```

## Platform-Specific Commands

### Linux Only

| Command | Description |
|---------|-------------|
| `service install` | Install the agent as a service (Linux only, non-packaged installs only, not required for DEB or RPM-based installations) |

**Example:**
```
Lithnet.AccessManager.Agent service install
```

### macOS Only

#### Secure Token Support

Manage secure token support for macOS:

```
Lithnet.AccessManager.Agent secure-token-support <command> [options]
```

Available commands:

| Command | Description |
|---------|-------------|
| `set` | Set initial credentials for a managed admin account with secure token |
| `get` | Show information about accounts configured for secure token support |
| `clear` | Clear stored credentials for secure token support |

Options for the `set` command:

| Option | Description |
|--------|-------------|
| `--username <username>` | The username of the account (required) |
| `--password <password>` | The password of the account (if omitted, you will be prompted) |

Options for the `clear` command:

| Option | Description |
|--------|-------------|
| `--username <username>` | The specific account to clear (if omitted, all accounts are cleared) |

**Examples:**
```
Lithnet.AccessManager.Agent secure-token-support set --username adminuser --password YOUR-PASSWORD
Lithnet.AccessManager.Agent secure-token-support set --username adminuser
Lithnet.AccessManager.Agent secure-token-support get
Lithnet.AccessManager.Agent secure-token-support clear
Lithnet.AccessManager.Agent secure-token-support clear --username adminuser
```

## Registration Modes

The agent supports different registration modes depending on the platform:

| Mode | Description | Platforms |
|------|-------------|-----------|
| `iwa` | Active Directory authentication (Integrated Windows Authentication/Negotiate) | All |
| `key` | AMS registration key authentication | All |
| `entra` | Microsoft Entra ID (formerly Azure AD) authentication | Windows only |

> **Note:** When using the `key` mode, you must also provide a registration key. Setting `--registration-key` automatically sets the registration mode to `key`.

## Administration Requirements

Many commands require administrator rights:
- Windows: Run Command Prompt or PowerShell as Administrator
- macOS/Linux: Use sudo or run as root

## Examples of Common Workflows

### Initial Setup

```
Lithnet.AccessManager.Agent setup
```

### Changing Server Configuration

```
Lithnet.AccessManager.Agent config --server new-server.example.com --port 8443
```

### Resetting the Agent

```
Lithnet.AccessManager.Agent reset --force
```

### Viewing Current Configuration

```
Lithnet.AccessManager.Agent show config
```

### Setting Up macOS Secure Token Support

```
Lithnet.AccessManager.Agent secure-token-support set --username adminuser
```

## Troubleshooting

If you encounter issues:

1. Ensure you're running with administrator rights
2. Check the agent logs
3. Try using the `show state` command to verify current agent state
4. Try resetting the agent with `reset --force`

For additional help, consult the full Lithnet Access Manager documentation.
