|

.. image:: images/access-manager-logo.png
   :align: center
   :alt: Access Manager Logo

|

Home
##############################################

Lithnet Access Manager is a tool that allows you to safely delegate sensitive administrative access to computers in your organization in a modern and user-friendly way.

It provides a web-based interface that allows users to request local admin/root passwords, BitLocker recovery keys, and grant just-in-time administrative access to their own accounts. 

It is fully compatible and works out-of-the-box with Microsoft LAPS, but also comes with its own agent, which expands LAPS coverage to Azure AD joined and registered devices, as well as macOS and Linux devices.

Access Manager provides a granular permission model, coupled with a detailed auditing system, both of which are extensible using PowerShell.

Modern authentication is a key feature of Access Manager, with support for OpenID Connect, allowing strong authentication and MFA with cloud-based identity providers such as Azure AD and Okta. On-premises providers have not been forgotten, with full support for WS-Federation (ADFS), smart cards, and if you need it, integrated windows authentication.

********************************************************************
Defend against ransomware and other lateral movement-based attacks
********************************************************************

Access Manager has one simple goal. To reduce the likelihood and impact of a wide-spread compromise in your environment by removing permanent administrative access to your workstations and servers. By making sure every computer has a unique local admin password (through the use of Microsoft LAPS or the Lithnet Access Manager Agent), and removing all other members of the built-in local `Administrators` group, you can limit the ability for credential-stealing ransomware to move laterally across your environment. Access Manager makes it as seamless as possible for admins to access LAPS passwords, or grant themselves temporary just-in-time admin access. Access Manager isn't a silver bullet guaranteed to protect you from this type of attack, but it forms a fundamental part of a defence-in-depth strategy against them. 

We recommend you have a look at our other product `Lithnet Password Protection for Active Directory <https://github.com/lithnet/ad-password-protection>`_, for a tool to help strengthen your environment against commodity password-based attacks. 

********************************************************************
Features
********************************************************************

Web-based access to local admin passwords
=================================================
Access Manager provides a simple web-based and mobile-friendly interface for accessing local admin passwords for Windows, macOS and Linux devices. There's no need for admins to install custom software, or have access to AD administrative tools to access LAPS passwords. 

.. image:: images/web-request-laps.gif
   :width: 400 
   :align: center

Administrators also have the option of forcing an expiry time when a password is accessed. This ensures that the password is rotated after use.

We use LAPS passwords ourselves, so we know they can be painful at times. We try to take away as much of that pain as possible. From using fonts where you can actually see the difference between a lower-case L and a capital I, to showing a breakdown of the password using the NATO phonetic alphabet to make it easy to read it out to someone. Have you ever found yourself needing to type a LAPS password into a Windows logon screen? Have Access Manager read the password to you while you type with its text-to-speech capability!
 
Whether you use Microsoft LAPS, or the Lithnet Access Manager agent, the user experience is the same.

Access historical local admin passwords
=================================================

Deploying the Lithnet Access Manager Agent to your fleet allows you to upgrade to encrypted local admin passwords and gain the benefit of having previous local admin passwords stored in the directory as well. This means no more issues getting locked out of computers when they are restored from backup or reverted from a snapshot.

.. image:: images/web-request-laps-history.gif
   :width: 400 
   :align: center 

Just-in-time administrative access to computers
=================================================
Using the same web interface, users can request that their account be added to a group that is a member of the local administrators group of the computer. This access is temporary and automatically removed after the allowed time period. Access Manager makes use of the Active Directory time-based membership feature in Windows Server 2016 and later domain functional levels, or time-based (dynamic) objects in earlier versions of AD.

.. image:: images/web-request-jit.gif
   :width: 400 
   :align: center

Easy access to BitLocker recovery passwords
=================================================
Authorized users can also request access to the BitLocker recovery passwords for a computer through the same easy-to-use web interface.

.. image:: images/web-request-bitlocker.gif
   :width: 400 
   :align: center

Audit success and failure event logs
=================================================
All success and failure events are logged to the Windows event log and a file. Optionally, you can send audit events via email, webhooks, and even PowerShell.

The webhook functionality makes it really easy to get alerts via Slack or Microsoft Teams, and there are even built-in templates for these systems.

.. image:: images/auditing-example-slack.png
   :align: center

Modern authentication options
=================================================

The web app supports traditional integrated windows authentication, as well as external authentication providers such as :doc:`ADFS </configuration/Setting-up-authentication-with-ADFS>` or 3rd party OpenID Connect providers such as 
:doc:`Azure AD </configuration/Setting-up-authentication-with-Azure-AD>` and :doc:`Okta </configuration/Setting-up-authentication-with-Okta>`. Using an external authentication provider allows you the option of providing additional protections for the application such as multifactor authentication.

******************************
Download the app
******************************

`Download the app </installation/Downloads>`_



.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: About Lithnet Access Manager

   Home <self>
   about-ams/Preventing-lateral-movement
   about-ams/Access-Manager-Editions
   about-ams/Licensing

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Installation

   installation/Getting-started
   installation/System-requirements
   installation/Downloads
   installation/Installing-the-Access-Manager-Server
   installation/Installing-the-Access-Manager-Agent

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Configuration

   configuration/Setting-up-authentication
   configuration/deploying-features
   configuration/importing/Importing-authorization-rules

.. toctree::
   :hidden:
   :maxdepth: 1
   :caption: Help and support

   help/Frequently-Asked-Questions
   help/Troubleshooting
   help/advanced
   help/app-pages/index.rst
   help/Getting-support
