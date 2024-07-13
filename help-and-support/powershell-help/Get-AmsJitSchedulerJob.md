---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsJitSchedulerJob

## SYNOPSIS
Gets the list of active just-in-time access jobs in the AMS scheduler

## SYNTAX

### GetByType (Default)
```
Get-AmsJitSchedulerJob [-Type <ScheduledTaskType>] [-FailedOnly] [<CommonParameters>]
```

### GetById
```
Get-AmsJitSchedulerJob [-Id] <String> [<CommonParameters>]
```

## DESCRIPTION
This cmdlet can be used to see the pending JIT removal tasks that are waiting in the scheduler.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsJitSchedulerJob
```

Gets a list of all jobs pending in AMS scheduler

### Example 2
```powershell
PS C:\> Get-AmsJitSchedulerJob -FailedOnly
```

Gets a list of all jobs in the AMS scheduler that have failed to successfully execute the JIT removal operation

### Example 3
```powershell
PS C:\> Get-AmsJitSchedulerJob -Id 'XXXXXX'
```

Gets a specific JIT scheduler job by its ID

## PARAMETERS

### -FailedOnly
Instructs the cmdlet to only return jobs that have failed to execute the JIT removal operation

```yaml
Type: SwitchParameter
Parameter Sets: GetByType
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
The ID of the job

```yaml
Type: String
Parameter Sets: GetById
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
The type of JIT scheduler job to return

```yaml
Type: ScheduledTaskType
Parameter Sets: GetByType
Aliases:
Accepted values: ActiveDirectoryGroupRemoval

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
## OUTPUTS

### Lithnet.AccessManager.PowerShell.ActiveDirectoryGroupMemberRemovalJobDetailsPSObject
## NOTES
In an Active Directory forest, with the \`Privilege Access Management\` feature enabled, AMS will use TTL-based group membership for Active Directory JIT tasks.
The AMS JIT scheduler will not be used, and no jobs will appear in the scheduler queue

## RELATED LINKS
