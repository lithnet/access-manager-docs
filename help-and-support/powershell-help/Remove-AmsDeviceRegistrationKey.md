---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsDeviceRegistrationKey

## SYNOPSIS
Removes a registration key

## SYNTAX

```
Remove-AmsDeviceRegistrationKey -Id <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet permanently deletes a registration key from the system. Devices will no longer be able to use the key to register with the AMS system.

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsDeviceRegistrationKey -Id 'd2162529-4ff6-4246-8147-0d2dfcbf76bf'
```

This example removes the cmdlet from the system by its known ID

### Example 2
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Key XXXXXX | Remove-AmsDeviceRegistrationKey
```

Searches for a registration key with the specified key value and removes it

### Example 3
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Name "Head office device registration key" | Remove-AmsDeviceRegistrationKey
```

Searches for a registration key with the specified name and removes it

## PARAMETERS

### -Force
Removes the registration key without prompting for confirmation 

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
The ID of the key

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Void

## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
