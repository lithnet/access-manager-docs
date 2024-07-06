# Setting up smart card authentication

Certificate-based authentication is provided by Access Manager, with the optional support for requiring smart-card authentication.

Certificates must contain a `principal name` attribute in their `Subject Alternative Names` which specifies the user's UPN as found in Active Directory.

Limited support is available for use of altSecurityIdentities in cases where certificates are used without a UPN, however these are not supported outside the forest where AMS is located.

## Configuring Access Manager

To use smart card authentication, where the smart cards are issued by an Active Directory-integrated certificate authority, configure Access Manager as follows.

1. Open the Lithnet Access Manager Service Configuration Tool
2. From the `App configuration/User authentication`, select `Smart card or other certificate` as the authentication provider
3. Select `Require smart card login extended key usage`
4. Select `Trust only Enterprise CAs registered in this domains NTAuth store`

![authentication\_smart card](../../images/ui-page-authentication-smartcard.png)

More advanced scenarios are supported through the use of being able to provide your own additional mandatory EKUs, or restricting authentication to specific issuers. Seek advice from your internal team that manages smart card issuance to if you are not sure if any of these settings are required.

## Identity resolution mode
In line with the certificate-based authentication changes announced by Microsoft in [KB5014754](https://support.microsoft.com/en-us/topic/kb5014754-certificate-based-authentication-changes-on-windows-domain-controllers-ad2c23b0-15d8-4340-a468-4d4f3b188f16), Access Manager by default now only accepts certificates containing the user's SID in an extension with OID `1.3.6.1.4.1.311.25.2`, or contained in a [SAN URL extension with the prefix](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-pkca/e8fd2c1d-50d3-493a-9b58-5e453850c567) `tag:microsoft.com,2022-09-14:sid:`.

If you are using older-style certificates, you need to select `Enable weak identity bindings` and select `enable UPN mapping`.

## Enabling altSecurityIdentities

If you do not use the SID or UPN fields in the certificate, and use the altSecurityIdentities capability in Active Directory to support certificates without a UPN, you'll need to perform some additional steps in AMS to enable this support.

The caveat with this implementation is that this only works in the forest that the AMS service is located within. As web-based certificate authentication happens at the TLS level, AMS is unable to prompt for a username or domain hint. Therefore, AMS can only search the local global catalog for the altSecurityIdentity values.

In line with the [Microsoft implementation](https://docs.microsoft.com/en-us/windows/security/identity-protection/smart-cards/smart-card-certificate-requirements-and-enumeration) for altSecurityIdentities, AMS searches the directory for a user match in the following order

```
X509:<I><S>^          Issuer and subject
X509:<S>*^            Subject
X509:<I><SR>          Issuer and serial number
X509:<SKI>            Subject key identifier
X509:<SHA1-PUKEY>     SHA1 public key
X509:<RFC822>*^       Email address 
```

> (\*) Use of these altSecurityIdentity types requires that certificate issuer validation against the NT Auth store is enabled

> (^) These altSecurityIdentity types are considered 'weak bindings' and require the use of the `Enable weak identity bindings` option.

## Certificate Forwarding

In certain scenarios - such as Access Manager running behind a TLS-terminating load balancer - certificate authentication may not work out of the box. Because the TLS connection is re-encrypted before it reaches Access Manager, the client certificate is not passed along to the server itself.

However, some load balancers or reverse proxies include a feature called 'Certificate Forwarding', where the load balancer validates the certificate, and passes the user's public key along as a header to the backend server (in this case, Access Manager).

This option allows you to specify a header which Access Manager will use to extract user certificates from for authentication.

It is important to note that, unless properly secured, any user may send this header to the Access Manager server - allowing impersonation. Therefore, Access Manager requires that you specify particular load balancers or proxies you expect to be using this feature. By default, even when enabled, Access Manager will reject all certificate headers unless the allowlists are populated.

### Examples

#### Nginx Reverse Proxy

1. Configure the server to receive client certificates with the [ssl_verify_client directive](https://nginx.org/en/docs/http/ngx_http_ssl_module.html#ssl_verify_client).
2. Configure the `X-Client-Cert` header to be forwarded to Access Manager.

This forwards the [$ssl_client_escaped_cert](https://nginx.org/en/docs/http/ngx_http_ssl_module.html#var_ssl_client_escaped_cert) variable, which is a URL-encoded version of the client certificate:

    ```
    # To avoid a client falsifying the header, first unset it.
    proxy_set_header Accept-Encoding "";
    proxy_set_header X-Client-Cert $ssl_client_escaped_cert;
    ```

####  Citrix ADC

You can follow [this guide](https://support.citrix.com/article/CTX217167/how-to-pass-client-certificate-to-backend-applications-that-requires-client-certificate-for-user-authentication-sslbridge) to insert to forward the client certificate as a header to Access Manager.