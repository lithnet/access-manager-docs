---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsDeviceRegistrationKeyGroup

## SYNOPSIS
Removes a group association from a registration key

## SYNTAX

```
Remove-AmsDeviceRegistrationKeyGroup -Id <String> -Groups <Object[]> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet removes one or more group associations from a registration key

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsDeviceRegistrationKeyGroup -Id 'ca546a0f-8b8d-4a47-862b-9d97c21f70ac' -Groups (Get-AmsGroup -Name "My devices")
```

Removes the group named "My devices" from the registration key specified by the ID

### Example 2
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Name "Head office devices" | Remove-AmsDeviceRegistrationKeyGroup -Groups (Get-AmsGroup -Name "My devices")
```

Gets a registration key by name, and removes the group named "My devices" from it

## PARAMETERS

### -Groups
The groups to remove

```yaml
Type: Object[]
Parameter Sets: (All)
Aliases:

Required: True
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
