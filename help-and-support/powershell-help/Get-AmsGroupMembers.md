---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsGroupMembers

## SYNOPSIS
Gets the members of an AMS group

## SYNTAX

```
Get-AmsGroupMembers -Id <String> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet gets the members of the specified AMS group

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsGroupMembers -Id 'ae48a8cb-6b54-457f-80cd-d0eb6437ec22'
```

Gets the membership of the group represented by the specified ID

### Example 2
```powershell
PS C:\> Get-AmsGroup -Name 'My devices' | Get-AmsGroupMembers
```

Gets the membership of the \`my devices\` group, by passing the group object into the pipeline

## PARAMETERS

### -Id
The ID of the group

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

### Lithnet.AccessManager.PowerShell.DevicePSObject
## NOTES
Use of this cmdlet requires an Enterprise Edition license.

## RELATED LINKS
