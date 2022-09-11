---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# New-AmsGroup

## SYNOPSIS
Creates a new AMS group

## SYNTAX

```
New-AmsGroup [-Name] <String> [-Description <String>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new AMS group, and optionally specifies a description for the group

## EXAMPLES

### Example 1
```powershell
PS C:\> New-AmsGroup -Name 'Head office macos devices' -Description 'Contains all macOS devices located in the corporate head office'
```

Creates a new AMS group with the specified name and description.

## PARAMETERS

### -Description
The description of the group

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

### -Name
The name of the group

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Lithnet.AccessManager.PowerShell.GroupPSObject

## NOTES

## RELATED LINKS
