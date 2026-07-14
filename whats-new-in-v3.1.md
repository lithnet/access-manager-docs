# What's new in Access Manager v3.1

Access Manager v3.1 moves the v3 release line to .NET 10. It contains no functional changes over an up-to-date v3.0 installation. Upgrading extends your support window and updates the operating systems the product supports.

## Extended support

Access Manager v3.0 reaches its end of support on 10 November 2026, in line with Microsoft .NET 8. Access Manager v3.1 is supported until 14 November 2028. See the [product lifecycle page](help-and-support/lifecycle.md) for all support dates.

## .NET 10

The Access Manager service, and the agents for macOS and Linux, now run on Microsoft .NET 10. The installers install the required runtime components automatically, and no manual runtime installation is needed.

## Operating system support changes

* Support for 32-bit (x86) versions of Windows has been dropped. The Windows agent is now available for x64 and arm64 only. Devices running 32-bit versions of Windows can continue to use the v3.0 agent until v3.0 reaches its end of support.
* Support for Fedora 43 and Fedora 44 has been added.
* Support for Debian 11, Ubuntu 20.04, Fedora 35 through 41, and macOS 13 has been removed, as these are not supported by .NET 10.

See [Upgrading from Access Manager v3.0](installation/upgrading-from-v3.0.md) for upgrade steps.
