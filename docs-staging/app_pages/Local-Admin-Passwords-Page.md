
<img src="images/ui-page-localadminpasswords.png" alt="local_passwords" width="1000px">

# Lithnet Access Manager agent
If you want to use the Lithnet Access Manager agent instead of the Microsoft LAPS agent, to take advantage of the password history and encryption capabilities, then you'll need to delegate appropriate permission for the AMS service account to read those passwords.

Click the `Delegate Lithnet AMA Permissions` button to generate a script to do this automatically.

<img src="images/ui-page-script-delegate-ama.png" alt="delegate_ama" width="1000px">


Copy or save the script, modify the `$OU` variable as appropriate, and run it in with domain admin rights.

# Encryption
