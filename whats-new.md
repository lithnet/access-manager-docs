# What's new in Lithnet Access Manager v2
Lithnet Access Manager v2 brings many new and exciting capabilities to our product. We've heard you loud and clear - you want LAPS everywhere in your organization! Well, the Access Manager Agent now supports managing local admin passwords on Azure AD joined and registered devices. We didn't stop there, we've added support for managing the root password on macOS and Linux, and even extended capability to managing LAPS passwords on Windows machines that are not joined to any domain at all!

Our other exciting new, and perhaps most requested feature, is extending our just-in-time access functionality to Active Directory groups. You can now define a role in Access Manager, and authorized users can claim that role, giving them time-limited membership in your customer AD group!

Read on to learn more about what else is new in Lithnet Access Manager.

## What's new in the Lithnet Access Manager Service
The most notable change to the service itself, is that AMS has moved from having an embedded database, to requiring a Microsoft SQL server. You can use Microsoft SQL Express, Standard, or Enterprise, as well as Azure SQL and Amazon RDS SQL. We've preconfigured a Microsoft SQL Express instance in our installer that is ready to go for small-to-medium sized deployments.

This database contains the app configuration and encrypted device passwords, so having a robust backup strategy is very important.

### New features
* Added support for reading local admin passwords stored in the new 'msLAPS' Active Directory attributes
* Added support for providing just-in-time access to an AD group (JIT for AD roles)
* Added support for storing local admin passwords in the AMS database for non-active directory-joined devices
* Added support for providing a computer name as a URL parameter in a computer access request
* Added support for auditing changes to authorization rules
* Enhanced audit template capabilities with conditional rendering using the handlebars language
* Added support for the new objectSID extension in user certificates when using certificate authentication
* Added the ability to deny login access to specific principals
* Added the ability to configure single-sign out when using OpenID Connect authentication
* Added support for modifying the event log audit template
* Configuration is now stored in the database, and configuration files are no longer used
* Removed the requirement for registry replication and shared stored when running AMS in a failover cluster
* Replaces the JIT mechanism for forests that don't support the Active Directory PAM feature with an internal scheduling engine
* Changes the 'request reason' setting from a global setting, to a per-authorization rule setting
* Removes the embedded database in favor of an SQL express or external SQL server
* Added support for Azure SQL databases
* Added support for Amazon RDS SQL databases
* Added support for setting up Access Manager behind layer 7 load balancers
* Users are now prompted to select a matching computer, when they supply an ambiguous computer name
* Added the ability to copy the LAPS username where available

### Deprecated features
* Custom audit scripts from Access Manager v1 have been replaced by 'v2' audit scripts. 'v1' scripts will continue to work for computer audit events, but should be updated to the new v2 script format to support new features and capabilities such as JIT for roles.

### Changed features
* Accessing encrypted passwords in Active Directory set by the Lithnet Access Manager Agent is now an Enterprise Edition feature
* The Lithnet Access Manager Service now requires Microsoft .NET 6.0 (was previously built on Microsoft .NET Core 3.1 which is EOL in December 2022)

## What's new in the Lithnet Access Manager Agent
Our agent is now based on Microsoft .NET 6.0, opening up cross-platform capabilities on operating systems when .NET is supported.

### New features
* Added support for managing local admin password on Azure AD-joined Windows devices
* Added support for managing local admin password on Azure AD-registered Windows devices
* Added support for managing local admin password on standalone Windows devices
* Added support for managing root password on macOS 
* Added support for managing root password on Linux
