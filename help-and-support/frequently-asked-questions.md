# Frequently asked Questions

## Do I need to deploy the Lithnet Access Manager Agent?

The Lithnet Access Manager Agent is only required if you have one of the following requirements

1. You want your local admin passwords encrypted in the directory
2. You want to store previous local admin passwords in the directory
3. You want to support Azure AD joined or Azure AD registered devices
4. You want to manage local admin passwords on non-Windows devices

If you want to use the Access Manager web app to access Microsoft LAPS passwords you do not need to use the Access Manager Agent.

Read our guide on [Choosing a local admin password strategy](../installation/installing-the-access-manager-agent/choosing-between-the-microsoft-and-lithnet-laps-agents.md) to learn more about the differences between using the Microsoft LAPS agent and the Lithnet Access Manager Agent.

## How are directory passwords encrypted?

Lithnet Access Manager uses public-key cryptography to protect directory passwords. The Access Manager Service (AMS) creates a public and private key pair (RSA-PSS 4096-bit), and stores the private key in the service certificate store.

The Access Manager agent (AMA) obtains the public key from either the directory, or the AMS server itself. It then generates a unique encryption key and salt and uses AES-CBC-256 to encrypt the password with this key. The AES key is encrypted with the public key of the encryption certificate and the resulting blob converted to base-64 text and stored along with the thumbprint of the certificate used to encrypt the key material.

## How do clients obtain the encryption certificate?

When using the Access Manager agent in Active Directory mode, the encryption certificate is located in the Configuration naming context, in the `caCertificate` attribute of an object with the name `CN=AccessManagerConfig,CN=Lithnet,CN=Services,CN=Configuration,DC=X`

When using the Access Manager agent in AMS directory mode, the encryption certificate is provided to the clients by the AMS server when they check in to see if their password needs to be changed.

## Can I rotate the encryption certificate?

Yes, you can create and publish a new encryption certificate at any time. Agents will encrypt their passwords using this new certificate at the next scheduled password rotation. Do note that the agents will not re-encrypt their previous passwords using the new certificates. Agents do not have access to the private key needed to decrypt the passwords.

As such, you need to ensure that the old certificate remains on the server, for as long as there are passwords in the directory that were encrypted with the old certificate.

## Can computers decrypt their own admin passwords?

No. Passwords are encrypted using asymmetrical encryption. They encrypt the passwords using the public key of the encryption certificate and only the private key can decrypt this data. The private key remains only on the AMS server at all times.
