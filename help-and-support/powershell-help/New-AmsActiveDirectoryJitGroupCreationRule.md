---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# New-AmsActiveDirectoryJitGroupCreationRule

## SYNOPSIS
Creates a new just-in-time Active Directory group creation rule

## SYNTAX

```
New-AmsActiveDirectoryJitGroupCreationRule [-ComputerOU <String>] [-CreateUnixGid <Boolean>]
 [-EnableJitGroupDeletion <Boolean>] [-GroupDescription <String>] [-GroupNameTemplate <String>]
 [-GroupOU <String>] [-GroupType <ActiveDirectoryGroupType>] [-Subtree <Boolean>]
 [-UnixGidAttributeName <String>] [-UnixGidStartRange <Int32>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new just-in-time Active Directory group creation rule

## EXAMPLES

### Example 1
```
PS C:\> New-AmsActiveDirectoryJitGroupCreationRule -ComputerOU "OU=Computers,DC=lithnet,DC=local" -GroupOU "OU=Groups,DC=lithnet,DC=local" -GroupNameTemplate "JIT-%ComputerName%" -GroupDescription "AMS JIT Group" -GroupType DomainLocal -CreateUnixGid $true -UnixGidAttributeName "gidNumber" -UnixGidStartRange 10000 -EnableJitGroupDeletion $true
```

In this example, a new JIT group creation rule is created that will create a new domain local group in the 'OU=Groups,DC=lithnet,DC=local' organizational unit. The group name will be 'JIT-<computername>', and the group description will be 'AMS JIT Group'. A unique Unix GID will be created for the group, and the group will be deleted when the computer is removed from the directory

## PARAMETERS

### -ComputerOU
The OU that will be used to searched for computer objects

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

### -CreateUnixGid
Specifies if AMS should create a unique Unix GID for the group

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableJitGroupDeletion
Specifies if AMS should delete the group when the computer is removed from the directory

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupDescription
The description of the rule

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

### -GroupNameTemplate
The template used to create the group name

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

### -GroupOU
The OU that the groups will be created in

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

### -GroupType
The type of AD group to create

```yaml
Type: ActiveDirectoryGroupType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subtree
Specifies if AMS should search child organizational units of the 'ComputerOU' for computer objects

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnixGidAttributeName
The name of the LDAP attribute to populate with the group's unique unix GID

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

### -UnixGidStartRange
The starting range of Unix GIDs to use

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### Lithnet.AccessManager.PowerShell.ServiceConfigPSObject
## NOTES

## RELATED LINKS
