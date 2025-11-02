# Managing TLS certificate automation

With the CA/Browser Forum announcing that the maximum lifetime of TLS certificates will be reduced to 47 days in 2029, automating the issuance and renewal of TLS certificates has become increasingly important. This guide provides an overview of options for automating TLS certificate management with Access Manager.

## Using Certify The Web

Certify The Web (CTW) is a popular ACME client for Windows that can automatically issue and renew certificates, then deploy them to Windows HTTP.SYS (the HTTPS stack used by Access Manager Server).

This example uses Let’s Encrypt as the default Certificate Authority (CA), but CTW supports others. See the [Certify getting started](https://docs.certifytheweb.com/docs/intro) and [requesting certificates](https://docs.certifytheweb.com/docs/certificate-process) guides for installation and configuration.

### Prerequisites

- Local administrator rights on the server
- The public DNS name(s) that users will browse to for Access Manager
- Outbound internet access from the server to your chosen CA (e.g., Let’s Encrypt)

### Step-by-step

1. Download and install Certify The Web on the Access Manager Server. Launch the app as an administrator.
2. Close the Access Manager Configuration app if it is open.
3. Click the **New Certificate** button.
4. In the **Identifiers** section, leave **Select site (optional)** set to **No Site Selected**. This setting applies only to IIS sites.
5. In **Add domains to certificate**, add the DNS name(s) used to access Access Manager (for example, ams.contoso.com). Click + to add each name.
6. Modify any other settings as needed in the **Advanced** tab, or leave defaults (e.g., certificate authority, account email).
7. In **Authorization**, configure the appropriate validation method:
    - HTTP-01 (requires port 80 reachable externally), or
    - DNS-01 via your DNS provider integration (required for wildcard names).
8. In **Deployment**, select **Certificate store Only** as the deployment mode.
9. In **Tasks**, add a new task of type **Update Port Binding**. On **Task Parameters**, use:
    - IP/Port: `0.0.0.0`
    - Port: `443`
    - AppId (GUID): `4C3E21BA-7BEF-46C8-BC85-A4407DB6F596`
10. Save the certificate configuration.
11. Click **Request Certificate** to perform the initial issuance and deployment.
12. Open the Access Manager Configuration app, navigate to the **Host configuration** page, and ensure the correct certificate is selected.
13. Browse to Access Manager over HTTPS to confirm the new certificate is in use.
14. CTW will now auto-renew and re-run the deployment tasks to keep the binding up to date.


## Manually using netsh

If you prefer not to use Certify The Web, or have another automation tool in use, you can update the  TLS binding manually. Run the following commands from an elevated PowerShell or Command Prompt on the Access Manager Server.

1. Import the new certificate (with private key) into Local Computer > Personal (My) using the Certificates MMC or PowerShell. Note the certificate's SHA-1 thumbprint and remove any spaces.
2. Remove the existing HTTPS binding for port 443:

```powershell
netsh http delete sslcert ipport=0.0.0.0:443
```

3. Add the new binding, replacing YOURTHUMBPRINT with the certificate's SHA-1 thumbprint. The AppId and IP/Port must be exactly as shown for Access Manager Server to recognize the binding. Changing these values is not supported and will confuse the UI.

```powershell
netsh http add sslcert ipport=0.0.0.0:443 certhash=YOURTHUMBPRINT appid={4C3E21BA-7BEF-46C8-BC85-A4407DB6F596}
```

4. Verify the binding:

```powershell
netsh http show sslcert ipport=0.0.0.0:443
```

5. Test HTTPS access to Access Manager. Once confirmed, you may remove the old certificate from the certificate store if it is no longer needed.

Note: The AppId and binding of `0.0.0.0:443` are required by Access Manager Server. Do not change these values.

