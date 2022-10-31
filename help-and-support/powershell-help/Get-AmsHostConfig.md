---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsHostConfig

## SYNOPSIS
Gets the current configuration specific to the AMS host

## SYNTAX

```
Get-AmsHostConfig [<CommonParameters>]
```

## DESCRIPTION
This cmdlet gets the current configuration of the AMS host where this PowerShell cmdlet is run. Host configuration is specific to the individual host, and is not shared by cluster members. 

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsHostConfig
```

This example gets the current configuration of the AMS host

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Lithnet.AccessManager.PowerShell.HostConfigurationOptionsPSObject
## NOTES

## RELATED LINKS
