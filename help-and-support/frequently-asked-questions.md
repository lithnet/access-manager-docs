# Frequently asked Questions

## Do I need to deploy the Lithnet Access Manager Agent?

The Lithnet Access Manager agent is an optional component you can deploy in your environment that provides a host of additional features that compliments the Access Manager server.

You should deploy the agent when you want to take advantage of the following capabilities
* Using the RapidLAPS passwordless LAPS login feature
* Using passphrases for LAPS passwords, instead of random characters
* Backing up BitLocker recovery keys from AD-joined, Entra-joined, and standalone Windows devices
* Managing the root password on macOS and linux devices

If you want to use our RapidLAPS feature for passwordless LAPS login and elevation, then the Access Manager Agent is required, however it does not need to be configured to manage the LAPS password itself. The agent can be deployed, and RapidLAPS enabled, while the Microsoft agent manages the LAPS password itself.

Read our guide on [Choosing a local admin password strategy](choosing-between-the-microsoft-and-lithnet-laps-agents.md) to learn more about the differences between using the Microsoft LAPS agent and the Lithnet Access Manager Agent.

## How are directory passwords encrypted?

Lithnet Access Manager uses public-key cryptography to protect directory passwords. The Access Manager Service (AMS) creates a public and private key pair (RSA-PSS 4096-bit), and stores the private key in the service certificate store.

The Access Manager agent obtains the public key from the AMS server as part of its policy. It then generates a unique encryption key and salt and uses AES-CBC-256 to encrypt the password with this key. The AES key is encrypted with the public key of the encryption certificate and the resulting blob converted to base-64 text and stored along with the thumbprint of the certificate used to encrypt the key material.

## Can I rotate the encryption certificate?

Yes, you can create and publish a new encryption certificate at any time. Agents will encrypt their passwords using this new certificate at the next scheduled password rotation. Do note that the agents will not re-encrypt their previous passwords using the new certificates. Agents do not have access to the private key needed to decrypt the passwords.

As such, you need to ensure that the old certificate remains on the server, for as long as there are passwords in the directory that were encrypted with the old certificate.

## Can computers decrypt their own admin passwords?

No. Passwords are encrypted using asymmetrical encryption. They encrypt the passwords using the public key of the encryption certificate and only the private key can decrypt this data. The private key remains only on the AMS server at all times.
