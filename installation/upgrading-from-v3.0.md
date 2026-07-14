# Upgrading from Access Manager v3.0 to v3.1

Access Manager v3.1 is a platform release that moves the product to .NET 10. Access Manager v3.0 is supported until 10 November 2026, and v3.1 is supported until 14 November 2028. See the [product lifecycle page](../help-and-support/lifecycle.md) for all support dates.

If you are upgrading from Access Manager v2, follow the [v2 upgrade guide](upgrading-from-v2.md) instead.

## Upgrading the Access Manager Server

v3.1 is an in-place upgrade from v3.0. Run the v3.1 'Access Manager Service' installer over the top of the existing installation. The v3.0 configuration and database are compatible with v3.1, and no configuration changes are required. The installer automatically installs the required .NET 10 runtime components.

As a best practice precaution, we recommend taking a backup of the server and database before performing the upgrade.

If you run a load-balanced farm, all nodes must be updated at the same time. This applies to every Access Manager upgrade, as database schema changes can be introduced in any release.

## Upgrading the Access Manager Agents

The v3.1 agent uses the same server API as v3.0, so agents and the server can be upgraded in either order.

The v3.1 agents install over the top of the existing v3.0 agents on all platforms. Note the following operating system support changes before planning your agent rollout:

* The v3.1 Windows agent is available for x64 and arm64 only. Devices running 32-bit versions of Windows can continue to use the v3.0 agent until v3.0 reaches its end of support.
* The v3.1 agents for Linux and macOS are not available for Debian 11, Ubuntu 20.04, Fedora 35 through 41, or macOS 13, as these operating systems are not supported by .NET 10.
