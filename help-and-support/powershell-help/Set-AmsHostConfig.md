---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsHostConfig

## SYNOPSIS
Sets one or more AMS host configuration parameters

## SYNTAX

```
Set-AmsHostConfig [-ApiEnabled <Boolean>] [-WebAppEnabled <Boolean>] [-ExternalHostname <String>]
 [-LogPath <String>] [-ConfigPath <String>] [-ConnectionString <String>] [-SkipConnectionStringValidation]
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to specify settings that apply to the specific host where the cmdlet is run.
These settings are not shared between hosts in a farm, and must be set on each individual AMS server where appropriate.

Note, you must restart the service after making changes with this cmdlet for those changes to take effect.

## EXAMPLES

### Example 1 - Enable the Access Manager API
```powershell
PS C:\> Set-AmsHostConfig -ApiEnabled $true -ApiHostName "ams.lithnet.local"
```

This example enables the AMS API, specifying a hostname of "ams.lithnet.local".
This is the hostname that agents use to connect to the service, and must match exactly what is configured on the client side.

### Example 2 - Turn off the Web app
```powershell
PS C:\> Set-AmsHostConfig -WebAppEnabled $false
```

This example disables the web app, preventing user access.

### Example 3 - Modify the log location
```powershell
PS C:\> Set-AmsHostConfig -LogPath "C:\Logs\AMS"
```

This example changes the log location to "C:\Logs\AMS"

## PARAMETERS

### -ApiEnabled
Enables or disables the API service

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigPath
The path where the applications config files are stored

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
The connection string used to connect to the database

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
The path where the applications log files are stored

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipConnectionStringValidation
Skips the process of validating the connection string.
Used when the user performing the action does not have access to the database itself

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebAppEnabled
Enables or disables the web app

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalHostname
Sets the external hostname for the service.
This is the hostname that agents use to connect to the service, and must match exactly what is configured on the client side.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### Lithnet.AccessManager.PowerShell.HostConfigurationOptionsPSObject
## NOTES

## RELATED LINKS
