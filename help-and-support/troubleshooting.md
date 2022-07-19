# Troubleshooting 

## Logs
The first step of any troubleshooting endeavour is check in the Access Manager log files. These contain information about errors and other important events. 

### Access Manager Service
The Access Manager Service has several log files. 

`access-manager-webapp.log` Contains events from the Access Manager web app, including information on access requests and authorization results.

`access-manager-api.log` Contains events from the Access Manager API, including things like device authentication, registration and password updates.

`access-manager-service.log` Contains events from the core access manager service, the scheduler, RPC interface, and worker services.

`access-manager-jitworker.log` Contains events from the JIT worker service, which is responsible for creating and deleting JIT groups for computer objects when this feature is enabled.

These logs are located in `%ProgramFiles%\Lithnet\Access Manager Service\Logs`

### Access Manager Agent
The Access Manager Agent log files are located in `%ProgramFiles%\Lithnet\Access Manager Agent\Logs`

### Configuration Tool
The configuration UI also has a log file to keep track of any issues encountered in the tool itself. The log file is called `access-manager-ui.log` and is located in `%ProgramFiles%\Lithnet\Access Manager Service\Logs`
