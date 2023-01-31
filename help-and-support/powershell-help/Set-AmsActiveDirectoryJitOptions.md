---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsActiveDirectoryJitOptions

## SYNOPSIS
Sets Active Directory JIT-related configuration

## SYNTAX

```
Set-AmsActiveDirectoryJitOptions [-JitMode <String>] [-DcLocatorMode <JitDcLocatorMode>]
 [-DeltaSyncIntervalMinutes <Int32>] [-FullSyncIntervalMinutes <Int32>]
 [-MaximumJitRemovalRetryAttempts <Int32>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to configure the behavior of the JIT engine for Active Directory

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-AmsActiveDirectoryJitOptions -JitMode JitScheduler
```

Sets the JIT engine to use its internal scheduler, rather than the Active Directory privileged access management feature (PAM). 

### Example 2
```powershell
PS C:\> Set-AmsActiveDirectoryJitOptions -DcLocatorMode SiteLookup,LocalDcLocator
```

Sets the JIT engine to use the SiteLookup and LocalDcLocator strategies when processing computer-based JIT requests

### Example 3
```powershell
PS C:\> Set-AmsActiveDirectoryJitOptions -DeltaSyncIntervalMinutes 5 -FullSyncIntervalMinutes 60
```

Sets the Active Directory JIT group creation scheduler to perform delta checks every 5 minutes, and full synchronization every 60 minutes.

## PARAMETERS

### -JitMode
Specifies the mechanism that AMS will use to perform JIT operations against Active Directory. Specifying `Auto` will use the Active Directory PAM feature, if it is available, otherwise the JIT scheduler will be used. Specifying `JitScheduler` will force the use of the scheduler, even if PAM is available.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Auto, JitScheduler

Required: False
Position: Named
Default value: Auto
Accept pipeline input: False
Accept wildcard characters: False
```

### -DcLocatorMode
Specifies the mechanisms that AMS will use to find the best domain controller to perform the Active Directory JIT operation for computer access requests. When set to `Default`, AMS will first try `RemoteDcLocator` which will contact the target computer, to ask which DC it is currently connected to. If it is not successful, AMS attempts a `SiteLookup` to try and match the computers IP address to an AD site, and that site's domain controller. Finally, if that is not successful, AMS will use its `LocalDcLocator` service to find its own DC and perform the group operation there. If you find JIT requests are taking a long time to process, set this value to `SiteLookup,LocalDcLocator` to bypass the `RemoteDcLocator` lookup process.

```yaml
Type: JitDcLocatorMode
Parameter Sets: (All)
Aliases:
Accepted values: Default, LocalDcLocator, RemoteDcLocator, SiteLookup

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeltaSyncIntervalMinutes
When AMS is configured to automatically create JIT groups for computers in Active Directory, this value sets the interval of time, in minutes, that AMS will check for new computers

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullSyncIntervalMinutes
When AMS is configured to automatically create JIT groups for computers in Active Directory, this value sets the internal of time, in minutes, that AMS will perform a full sync of computer and group objects, and delete any groups for computers that no longer exist

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumJitRemovalRetryAttempts
When AMS is using its internal scheduler to perform JIT removal operations, this is the maximum number of attempts it will make to revoke JIT access before abandoning the request

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 80
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Lithnet.AccessManager.PowerShell.JitConfigurationOptionsPSObject

## NOTES

## RELATED LINKS
