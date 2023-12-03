# System Requirements

## Access Manager Server (AMS) Operating System Support

### Operating system requirements

The Lithnet Access Manager Service requires Windows Server 2016 or higher.

#### Dependencies

* [.NET Desktop Runtime](https://dotnet.microsoft.com/download/dotnet-core/6.0/runtime) 6.0.10 or later installed
* [.NET Hosting Bundle](https://dotnet.microsoft.com/download/dotnet-core/6.0/runtime) 6.0.10 or later installed
* Microsoft SQL Express 2019 (if hosting the database locally), SQL Server 2017 or later (Standard or Enterprise edition), Azure SQL or an Amazon RDS SQL database. (SQL express is installed by default). See the [SQL installation options](installing-the-access-manager-server/sql-installation-options.md) page for more details

## Access Manager Agent (AMA) Operating System Support

The Lithnet Access Manager agent is supported on Windows, macOS, and Linux. Each operating system family has slightly different requirements.

### Windows requirements

#### Dependencies

The agent requires the installation of .NET Framework 4.7.2 or later if it is not already installed as part of the OS for x86 and x64 installations. For arm64 installations, .NET 6.0 is required.

#### Supported versions

* x64 Windows 8.1 or later
* x86 Windows 8.1 or later
* arm64 Windows 10 or later

#### Password storage

* Domain joined clients will store their password in the Active Directory. This requires Active Directory schema extensions to be present.
* Non domain-joined clients will store their password in the AMS directory.

### macOS requirements

#### Supported versions

* OSX 10.15 (Catalina)
* macOS 11 (Big Sur) (Intel or M1)
* macOS 12 (Monterey) (Intel or M1)
* macOS 13 (Ventura) (Intel or M1)

#### Password storage

* macOS devices will store their password in the AMS directory.

### Linux requirements

#### Dependencies

The Access Manager Agent requires the use of the `chpasswd` tool that is built into most modern Linux systems.

#### Supported versions

The agent runs on .NET 6.0 and should work on any Linux distribution supported by Microsoft for these platforms.

Lithnet provides packages for RPM and Debian-based distributions, as well as tar.gz file for use with others.

See the [Microsoft guide for supported operating systems for .NET 6.0](https://github.com/dotnet/core/blob/main/release-notes/6.0/supported-os.md)

The following operating system versions have been tested and are fully supported by Lithnet.

| Distribution | Version | Architecture |
| ------------ | ------- | ------------ |
| Ubuntu       | 18.04   | x64/arm64    |
| Ubuntu       | 20.04   | x64/arm64    |
| Ubuntu       | 22.04   | x64/arm64    |
| RHEL         | 7       | x64          |
| RHEL         | 8       | x64/arm64    |
| RHEL         | 9       | x64/arm64    |
| Fedora       | 35      | x64/arm64    |
| Fedora       | 36      | x64/arm64    |
| Fedora       | 37      | x64/arm64    |
| Fedora       | 38      | x64/arm64    |
| Fedora       | 39      | x64/arm64    |
| Debian       | 9       | x64          |
| Debian       | 10      | x64/arm64    |
| Debian       | 11      | x64/arm64    |
| Debian       | 12      | x64/arm64    |

#### Password storage

* Linux devices will store their password in the AMS directory.
