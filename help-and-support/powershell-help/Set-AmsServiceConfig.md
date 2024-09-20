---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsServiceConfig

## SYNOPSIS
This cmdlet allows you to set the service-wide configuration for the Access Manager service

## SYNTAX

```
Set-AmsServiceConfig [-FarmApiHostName <String>] [-FarmApiPort <Int32>] [-FarmWebAppHostName <String>]
 [-FarmWebAppPort <Int32>] [-ForestsToIgnore <String[]>] [-DomainsToIgnore <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Settings that are configured here apply to all AMS servers in the farm. 

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsServiceConfig -FarmApiHostName "api.mycompany.com" -FarmWebAppHostName "app.mycompany.com"
```

This example sets the external host names for the AMS farm

## PARAMETERS

### -DomainsToIgnore
Specifies a list of trusted domains that should be ignored by AMS as they are typically unreachable

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FarmApiHostName
Specifies the external host name that agents will use to connect to the AMS farm.
If this value is not set, the 'ExternalHostName' property from each individual AMS server is used, which can be set using the Set-AmsHostConfig cmdlet.

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

### -FarmApiPort
Specifies the HTTPS port that agents will use to connect to the AMS farm.
If this value is not set, the default port of 443 is used

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FarmWebAppHostName
Specifies the external host name that end users will use to connect to the AMS farm.
If this value is not set, the 'ExternalHostName' property from each individual AMS server is used, which can be set using the Set-AmsHostConfig cmdlet.

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

### -FarmWebAppPort
Specifies the HTTPS port that end users will use to connect to the AMS farm.
If this value is not set, the default port of 443 is used

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForestsToIgnore
Specifies a list of trusted forests that should be ignored by AMS as they are typically unreachable

```yaml
Type: String[]
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

### Lithnet.AccessManager.PowerShell.ServiceConfigPSObject

## NOTES

## RELATED LINKS
