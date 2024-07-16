# System Requirements

## Access Manager Server (AMS) Operating System Support

### Operating system requirements

The Lithnet Access Manager Service requires Windows Server 2016 or higher.

#### Dependencies

* [.NET Desktop Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/8.0/runtime) 8.0.0 or later installed
* [.NET Hosting Bundle](hhttps://dotnet.microsoft.com/en-us/download/dotnet/8.0/runtime) 8.0.0 or later installed
* Microsoft SQL Express 2022 (if hosting the database locally), SQL Server 2019 or later (Standard or Enterprise edition), Azure SQL or an Amazon RDS SQL database. (SQL express is installed by default). See the [SQL installation options](installing-the-access-manager-server/sql-installation-options.md) page for more details

## Access Manager Agent Operating System Support

The Lithnet Access Manager agent is supported on Windows, macOS, and Linux. Each operating system family has slightly different requirements.

### Windows requirements

#### Dependencies

The agent requires the installation of .NET Framework 4.7.2 or later if it is not already installed as part of the OS for x86 and x64 installations. For arm64 installations, .NET Framework 4.8.1 is required.

#### Supported versions

* x64 Windows 10 / Windows Server 2016 or later
* x86 Windows 10 or later
* arm64 Windows 10 or later

### macOS requirements

#### Supported versions

* macOS 12 (Monterey) (Intel or ARM64)
* macOS 13 (Ventura) (Intel or ARM64)
* macOS 14 (Sonoma) (Intel or ARM64)

### Linux requirements

#### Dependencies

The Access Manager Agent requires the use of the `chpasswd` tool that is built into most modern Linux systems.

#### Supported versions

The agent runs on .NET 8.0 and should work on any Linux distribution supported by Microsoft for these platforms.

Lithnet provides packages for RPM and Debian-based distributions, as well as tar.gz file for use with others.

See the [Microsoft guide for supported operating systems for .NET 8.0](https://github.com/dotnet/core/blob/main/release-notes/8.0/supported-os.md)

The following operating system versions have been tested and are fully supported by Lithnet.

| Distribution | Version | Architecture |
| ------------ | ------- | ------------ |
| Ubuntu       | 20.04   | x64/arm64    |
| Ubuntu       | 22.04   | x64/arm64    |
| Ubuntu       | 24.04   | x64/arm64    |
| RHEL         | 8       | x64/arm64    |
| RHEL         | 9       | x64/arm64    |
| Fedora       | 35      | x64/arm64    |
| Fedora       | 36      | x64/arm64    |
| Fedora       | 37      | x64/arm64    |
| Fedora       | 38      | x64/arm64    |
| Fedora       | 39      | x64/arm64    |
| Debian       | 11      | x64/arm64    |
| Debian       | 12      | x64/arm64    |
