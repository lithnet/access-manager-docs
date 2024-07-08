# Installing the Access Manager Agent on Linux

## Prerequisites

The Access Manager Agent makes use of the `chpasswd` tool, built into most Linux distributions. Ensure this tool is available before installing the agent.

The agent must be able to validate the AMS server certificate. If you are using a private CA, or a self-signed certificate, consult the guide relevant to your OS for how to add the certificate to the OS trust store. You can use OpenSSL to validate the trust state of the certificate using the `openssl verify cert.crt` command.

The agent itself runs using systemd, and as it requires access to reset the root password, must be run as the root user.

### .NET requirements

The agent is build using Microsoft .NET 8.0. Ensure the distribution you are using is supported See the [Microsoft guide for supported operating systems for .NET 8.0](https://github.com/dotnet/core/blob/main/release-notes/8.0/supported-os.md) for more information.

## Agent installation

### Installing the agent on **Fedora** using the Lithnet repo

```shell
#!/usr/bin/env bash
​
# Ensure that the right DNF components are available
sudo dnf -y install dnf-plugins-core
​
# Add the Lithnet Fedora repository
sudo dnf config-manager --add-repo https://packages.lithnet.io/config/rpm/fedora/lithnet.repo 
```

If you are installing the agent for the first time, simply run:
> ```shell
> # Install the agent
> sudo dnf install LithnetAccessManagerAgent3
> ```

If you are *upgrading* the agent from version 2, ensure you include the `--allowerasing` argument to ensure the installation process can remove the old agent and migrate configuration:

> ```shell
> # Upgrade the agent (from version 2 to version 3)
> sudo dnf install LithnetAccessManagerAgent3 --allowerasing
> ```


### Installing the agent on **Red Hat** using the Lithnet repo

```shell
#!/usr/bin/env bash
​
# Ensure that the right DNF components are available
sudo dnf -y install dnf-plugins-core
​
# Add the Lithnet Fedora repository
sudo dnf config-manager --add-repo https://packages.lithnet.io/config/rpm/rhel/lithnet.repo 
```

If you are installing the agent for the first time, simply run:
> ```shell
> # Install the agent
> sudo dnf install LithnetAccessManagerAgent3
> ```

If you are *upgrading* the agent from version 2, ensure you include the `--allowerasing` argument to ensure the installation process can remove the old agent and migrate configuration:

> ```shell
> # Upgrade the agent (from version 2 to version 3)
> sudo dnf install LithnetAccessManagerAgent3 --allowerasing
> ```

### Installing the agent manually on RPM-based distributions

Use the appropriate package management tool to install the agent

```shell
# Download the Access Manager Agent data package
curl -L https://packages.lithnet.io/linux/rpm/prod/packages/access-manager-agent/v3.0/noarch/stable -o ~/accessmanager-data.rpm
sudo dnf install ~/accessmanager-data.rpm

# Download the x64 Access Manager Agent
curl -L https://packages.lithnet.io/linux/rpm/prod/packages/access-manager-agent/v3.0/x64/stable -o ~/accessmanager.rpm
sudo dnf install ~/accessmanager.rpm
```

### Installing the agent on **Debian** using the Lithnet repo

```shell
#!/bin/bash
​
# Install prerequisites
sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
​
# Import the Lithnet GPG signing keys
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://packages.lithnet.io/keys/lithnet.asc | sudo gpg --dearmor -o /etc/apt/keyrings/lithnet.gpg
sudo chmod a+r /etc/apt/keyrings/lithnet.gpg
​
# Add the Lithnet repository, specific to your build and architecture
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/lithnet.gpg] \
  https://packages.lithnet.io/linux/deb/prod/repos/debian/ \
  $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/lithnet.list > /dev/null
​
# Fetch the new repo
sudo apt update
```

If you are installing the agent for the first time, simply run:
> ```shell
> # Install the agent
> sudo apt install lithnetaccessmanageragent3
> ```

If you are *upgrading* the agent from version 2, ensure you include the `--autoremove` argument to ensure the installation process can remove the old agent and migrate configuration:

> ```shell
> # Upgrade the agent (from version 2 to version 3)
> sudo apt install lithnetaccessmanageragent3 --autoremove
> ```

### Installing the agent on **Ubuntu** using the Lithnet repo

```shell
#!/bin/bash
​
# Install prerequisites
sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
​
# Import the Lithnet GPG signing keys
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://packages.lithnet.io/keys/lithnet.asc | sudo gpg --dearmor -o /etc/apt/keyrings/lithnet.gpg
sudo chmod a+r /etc/apt/keyrings/lithnet.gpg
​
# Add the Lithnet repository, specific to your build and architecture
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/lithnet.gpg] \
  https://packages.lithnet.io/linux/deb/prod/repos/ubuntu/ \
  $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/lithnet.list > /dev/null
​
# Fetch the new repo
sudo apt update
```

If you are installing the agent for the first time, simply run:
> ```shell
> # Install the agent
> sudo apt install lithnetaccessmanageragent3
> ```

If you are *upgrading* the agent from version 2, ensure you include the `--autoremove` argument to ensure the installation process can remove the old agent and migrate configuration:

> ```shell
> # Upgrade the agent (from version 2 to version 3)
> sudo apt install lithnetaccessmanageragent3 --autoremove
> ```

### Installing the agent manually on Debian-based distributions

Use the appropriate package management tool to install the agent

```shell
# Download the Access Manager Agent data package
curl -L https://packages.lithnet.io/linux/deb/prod/packages/access-manager-agent/v3.0/noarch/stable -o ~/accessmanager-data.deb
sudo apt install ~/accessmanager-data.deb

# Download the x64 Access Manager Agent
curl -L https://packages.lithnet.io/linux/deb/prod/packages/access-manager-agent/v3.0/x64/stable -o ~/accessmanager.deb
sudo apt install ~/accessmanager.deb
```

### Installing the agent from the .tar.gz archive

Extract the archive to the root file system, allowing the files to be placed in their correct location. See the `File location` section below for more information on what files get unpacked and where.

While you do not need to install the .NET package itself, as the agent contains all the .NET components it needs to run, there are certain dependencies required by .NET, that if are not present, will prevent the agent from running. If you run into this issue, you may wish to install the .NET 8.0 package to automatically obtain the dependencies, or [review the list of dependencies](https://docs.microsoft.com/en-us/dotnet/core/install/linux-scripted-manual) that .NET requires, and install these yourself.

Run the following command to register the service with systemd

```shell
/opt/LithnetAccessManagerAgent/Lithnet.AccessManager.Agent --install
```

Continue to the `Configuring the agent` section below.

## Configuring the agent

Once the package is installed, it must be configured to talk to your AMS server. You can run the following command to perform an interactive installation.

If your device is joined to an Active Directory domain, you can use Windows authentication (kerberos) to authenticate to the AMS server. Otherwise, you will need to create a registration key on the AMS server and use that instead.

```shell
/opt/LithnetAccessManagerAgent/Lithnet.AccessManager.Agent --setup
```

{% hint style="warning" %}
If the hostname provided does not match exactly the `External host name` value configured on the [Host configuration page](../../help-and-support/app-pages/host-configuration-page.md), the agent will fail to connect to the server
{% endhint %}

To perform a non-interactive installation, use the following command, replacing the server name, and registration key as appropriate. You can generate new registration keys using the AMS configuration tool.

Install the agent using a registration key
```shell
/opt/LithnetAccessManagerAgent/Lithnet.AccessManager.Agent --server ams.lithnet.local --registration-key XXXX
```

Install the agent using Windows authentication (kerberos)
```shell
/opt/LithnetAccessManagerAgent/Lithnet.AccessManager.Agent --server ams.lithnet.local --registration-mode iwa 
```

Check the log using the instructions in the `Viewing the log files` section below to ensure the agent registered correctly.

## Validate agent installation

On the Access Manager server, go to the `Access Manager Agent/Devices` page, and ensure that the devices you installed the agent on have appeared in the device list. If you configured your registration key to require manual approval, you must approve the devices before they can be accessed.

## Restarting the agent

The Lithnet Access Manager Agent runs as a daemon using systemd. You can use standard systemd commands to start, stop and restart the agent.

```shell
systemctl restart LithnetAccessManagerAgent
```

## Viewing log files

The agent logs are viewed using `journalctl`.

To show all events in the log use the following command

```shell
journalctl -u LithnetAccessManagerAgent -p 7 -a
```

To show a live stream of log messages use the following command

```shell
journalctl -u LithnetAccessManagerAgent -p 7 -a -f
```

## File locations

The agent creates and uses the following files and folders.

`/etc/LithnetAccessManagerAgent.conf` - The main configuration file for the application. This contains the AMS server name and other settings relevant to the application.

`/var/lib/LithnetAccessManagerAgent/LithnetAccessManagerAgent.state` - This contains information used by the agent to store its current state information. This file should not be modified. It is generated by the app when it is run, and is not part of the installation package.

`/opt/LithnetAccessManagerAgent` - This directory contains the application binary files.

`/etc/systemd/system/LithnetAccessManagerAgent.service` - The systemd entry for the agent
