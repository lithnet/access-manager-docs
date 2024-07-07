# Authentication configuration page

The Access Manager web service allows you to choose one of several types of authentication providers. It is recommended to use modern authentication using a mechanism such as OpenID Connect, where an identity provider can provider high assurance authentication utilizing password-less or multifactor authentication.

Access Manager supports modern identity providers such as Microsoft Entra and Okta out of the box.

## OpenID Connect

OpenID Connect is the preferred authentication provider. Coupled with a modern IDP like Microsoft Entra or Okta, you can provide strong authentication to your application, backed up by multifactor authentication. See the guides for setting up Access Manager to work with [Microsoft Entra](../../configuration/setting-up-authentication/setting-up-authentication-with-azure-ad.md) or [Okta](../../configuration/setting-up-authentication/setting-up-authentication-with-okta.md).

Using OpenID Connect requires that your identity provider pass a `upn` claim containing the on-premises Active Directory UPN of your users.

### Sign out mode
When users click the logout button, you can choose for them to be logged out of the application, or have Access Manager request that the user be signed out of the IDP (where supported by the IDP).

![](../../images/ui-page-authentication-oidc-azure.png)

## WS-Federation

WS-Federation can be used to delegate the authentication process to an on-premises ADFS or similar product. Read the [setup guide](../../configuration/setting-up-authentication/setting-up-authentication-with-adfs.md) for configuring Access Manager to work with ADFS.

Using WS-Federation requires that your identity provider pass a `upn` claim containing the on-premises Active Directory UPN of your users.

## Smart-card or other certificate

Certificate-based authentication is provided by Access Manager, with the optional support for requiring smart-card authentication.

Read the [guide for setting up smart card authentication](../../configuration/setting-up-authentication/setting-up-smart-card-authentication.md) to learn more about supported certificate mappings and attributes.

![](../../images/ui-page-authentication-smartcard.png)

### Require 'Smart Card Logon' enhanced key usage
Enabling this setting requires that user's certificate must contain the `Smart Card Logon` EKU.

### Additional mandatory EKUs

Specify any custom EKUs that must be present in the certificate for the authentication to be successful.

### Certificate issuer validation

You must select how you want to validate the certificate issuer. Note that no matter which validation option is selected, at a minimum all certificates must be validated up to a trusted CA on the machine that runs AMS.

#### Trust only Enterprise CAs registered in this domain's 'NTAuth' store

Active Directory Enterprise CAs are automatically registered in the directory itself as trusted issuers. CAs in the Enterprise `NTAuth` store are trusted to issue logon certificates within the domain. If you select this option, then only certificates issued by one of these CAs are trusted. (Recommended options for smart card certificates)

#### Trust only these specific issuers

This option allows you to import a specific certificate authority's certificate that must be present in the certificate chain for it to be accepted. This can be a subordinate CA, rather than a root certificate. You can add multiple trusted issuers to this list, but only one of them needs to be present in the client's certificate chain.

### Certificate Forwarding

In certain scenarios - such as Access Manager running behind a TLS-terminating load balancer - certificate authentication may not work out of the box. Because the TLS connection is re-encrypted before it reaches Access Manager, the client certificate is not passed along to the server.

However, some load balancers or reverse proxies include a feature called *Certificate Forwarding*, where the load balancer validates the certificate, and passes the user's public key along as a header to the backend server (in this case, Access Manager).

This option allows you to specify a header which Access Manager will use to extract user certificates from for authentication.

It is important to note that, unless properly secured, any user may send this header to the Access Manager server - allowing impersonation. Therefore, Access Manager requires that you specify particular load balancers or proxies you expect to be using this feature. By default, even when enabled, Access Manager will reject all certificate headers unless the allowlists are populated.

## Integrated Windows Authentication

The Integrated Windows Authentication (IWA) provider allows users to log in with NTLM or Kerberos authentication. 

Ensure you read the guide on [setting up windows authentication](../../configuration/setting-up-authentication/setting-up-integrated-windows-authentication.md) to learn how to correctly configure the SPN.

![](../../images/ui-page-authentication-iwa.png)

### Authentication Scheme

Select one of the following authentication options

* Basic: Uses basic authentication (username/password) - Not recommended
* NTLM: Use NTLM authentication only
* Negotiate: Use Kerberos if possible, otherwise fall back to NTLM

## Sign-in restrictions
### Authorized users and groups
Specify the users and groups that should be allowed to log into this service, or leave the field blank to allow anyone who successfully authenticates to log in

### Denied users and groups
Add any users and groups that should be denied login to this service. Users in this group will not be able to log in even if they are in the `Authorization users and groups` list.