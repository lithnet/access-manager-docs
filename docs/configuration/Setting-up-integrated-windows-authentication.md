# Setting up integrated windows authentication

The following guide will assist you in configuring your application to use Integrated Windows Authentication (IWA).

Note, that we recommend that you use a strong authentication mechanism such as OpenID Connect, where you have the ability to enforce multifactor authentication on users attempting to access your application. Access Manager fully supports modern OIDC providers such as [Azure AD](Setting-up-authentication-with-Azure-AD) and [Okta](Setting-up-authentication-with-Okta). 

## Part 1: Configure the SPN
Lithnet Access Manager uses kernel-mode authentication, which means the computer account, rather than the service account is used to authenticate the client. This means that the Kerberos service principal name must be applied to the computer account, rather than the service account.

If your web url hostname is different to your machines AD hostname, then you'll need to register an SPN for this hostname.

Run the following command to set the SPN. Replace {dnsName} with the hostname web clients will use to access the service and {computerNetBIOSName} with the AD computer name

```
setspn -s HTTP/{dnsName} {computerNetBIOSName}
```

For a website called `accessmanager.lithnet.local` running on computer `AMSWEB01`, the command would be

```
setspn -s HTTP/accessmanager.lithnet.local AMSWEB01
```

## Part 2: Configure Lithnet Access Manager

<img src="../images/ui-page-authentication-iwa.png" alt="!" width="1000px">

1. Open the Lithnet Access Manager Service Configuration Tool
2. Select the `Server configuration\User Authentication` page
3. Select `Integrated windows authentication` as the authentication provider
4. Select `Negotiate` for the authentication scheme. 

```{warning}
The use of NTLM and basic auth is not recommended and are provided for testing purposes only.
```

To restrict clients to the use of Kerberos only, disable incoming NTLM authentication for the server using [group policy](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/network-security-restrict-ntlm-incoming-ntlm-traffic).