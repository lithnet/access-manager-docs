---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Set-AmsActiveDirectoryJitGroupCreationRule

## SYNOPSIS
Sets one or more properties of an excisting just-in-time Active Directory group creation rule

## SYNTAX

```
Set-AmsActiveDirectoryJitGroupCreationRule -Id <String> [-ComputerOU <String>] [-CreateUnixGid <Boolean>]
 [-EnableJitGroupDeletion <Boolean>] [-GroupDescription <String>] [-GroupNameTemplate <String>]
 [-GroupOU <String>] [-GroupType <ActiveDirectoryGroupType>] [-Subtree <Boolean>]
 [-UnixGidAttributeName <String>] [-UnixGidStartRange <Int32>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet sets one or more properties of an existing just-in-time Active Directory group creation rule

## EXAMPLES

### Example 1
```
PS C:\> Set-AmsActiveDirectoryJitGroupCreationRule -Id "12345678-1234-1234-1234-123456789012" -CreateUnixGid $true -UnixGidAttributeName "gidNumber" -UnixGidStartRange 10000	 -EnableJitGroupDeletion $true	-GroupDescription "AMS JIT Group" -GroupNameTemplate "JIT-%ComputerName%" -GroupOU "OU=Groups,DC=lithnet,DC=local" -ComputerOU "OU=Computers,DC=lithnet,DC=local" -Subtree $true
```

Sets the properties of the JIT group creation rule with the specified ID

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
Specifies if AMS should create a unique unix GID for the group

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

### -Id
The ID of the rule

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

### Lithnet.AccessManager.PowerShell.JitConfigurationOptionsPSObject
## NOTES

## RELATED LINKS
