# Host configuration page
Settings on this page apply to the physical host computer only. If you have more than one Access Manager server, these settings will be unique to each server.

![](../../images/ui-page-host-configuration.png)

## App version and updates
Shows the current application version, and optionally shows you if there is a new version of the application available. You can prevent the application from checking for updates, by disabling the `Enable update checks` option. Note that this only checks to see if updates are available. Updates must always be downloaded and installed manually.

## Service account

Specifies the service account that runs the Access Manager Service application. Use a group-managed service account where ever possible.

Before you change the service account, make sure the database permissions allow the new account to connect. If you are using the built-in SQL express database, you do not need to make any manual changes.

## TLS/SSL Certificate

### Certificate

Specify the TLS certificate used to protect HTTPS traffic to and from the website. You can select a certificate from the local machine store, or import a PFX file.

### Certificate expiry

Shows how long until the currently selected certificate expires.

## HTTP configuration

### HTTP Port

The HTTP port that the application will listen on. The default is port 80. Note that this port is only used to redirect connections to HTTPS. The application won't serve content over non HTTPS connections.

### HTTPS Port

The HTTPS port that the application will listen on. The default is port 443.

## Web app configuration

### Enable the web app
When enabled, this host will serve the Access Manager web app. You can disable this if you want to have an API-only or configuration-only host.

## API configuration

### Enable the Access Manager API
When enabled, the Access Manager service API is activated, allowing devices with the Lithnet Access Manager Agent installed to communicate with this server and manage their local admin passwords.

### API host name

When the Access Manager API is enabled, you must specify a valid DNS name that will be used by Access Manager Agents to contact this host. This name must match exactly with the AMS server name configured on the agents themselves, and it must be present in the HTTPS certificate used by the service.

:::{admonition} Warning :class: warning If this value differs from the AMS server name configured in the agent at installation time, the agent will be unable to communicate with the server :::
