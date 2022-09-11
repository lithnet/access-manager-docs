---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Export-AmsServerDiagnostics

## SYNOPSIS
This cmdlet is used to export diagnostic information that may be requested by Lithnet support

## SYNTAX

```
Export-AmsServerDiagnostics -File <String> [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### Example 1
```powershell
PS C:\> Export-AmsServerDiagnostics -File c:\diagnostics.txt
```

This example exports the diagnostics to a file called `c:\diagnostics.txt`

## PARAMETERS

### -File
The path to create the export file

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

## RELATED LINKS
