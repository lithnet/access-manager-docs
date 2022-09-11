---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Add-AmsDeviceRegistrationKeyGroup

## SYNOPSIS
Adds an AMS group to an existing registration key

## SYNTAX

```
Add-AmsDeviceRegistrationKeyGroup -Id <String> -Groups <Object[]> [<CommonParameters>]
```

## DESCRIPTION
A registration key can be associated with one or more AMS groups. When a device uses this key to register, it will automatically be added to the associated groups. This cmdlet allows you to add an AMS group to an existing registration key.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsDeviceRegistrationKey -Name 'my example key' | Add-AmsDeviceRegistrationKeyGroup -Groups '6efbd76f-befb-44df-9df7-80ef5660df5d'
```

## PARAMETERS

### -Groups
A collection of groups to add. This can be a group ID string, or a group object obtained from the `Get-AmsGroup` cmdlet

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
The ID of the registration key

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
