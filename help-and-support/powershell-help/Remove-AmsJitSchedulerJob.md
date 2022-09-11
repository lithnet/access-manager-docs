---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Remove-AmsJitSchedulerJob

## SYNOPSIS
Removes a job from the AMS scheduler

## SYNTAX

```
Remove-AmsJitSchedulerJob [-Id] <String> [<CommonParameters>]
```

## DESCRIPTION
The AMS JIT scheduler is responsible for removing JIT access from a user when their access time has expired. This cmdlet allows you to remove a job from the queue.

## EXAMPLES

### Example 1
```powershell
PS C:\> Remove-AmsJitSchedulerJob -Id 'XXXXXXXX'
```

Removes a JIT scheduler job from the queue.

## PARAMETERS

### -Id
The ID of the job

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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
In an Active Directory forest, with the `Privilege Access Management` feature enabled, AMS will use TTL-based group membership for Active Directory JIT tasks. The AMS JIT scheduler will not be used, and no jobs will appear in the scheduler queue

## RELATED LINKS
