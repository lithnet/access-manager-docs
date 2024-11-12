---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Get-AmsIdpClaimMapping

## SYNOPSIS
Gets the claim mappings for an identity provider

## SYNTAX

```
Get-AmsIdpClaimMapping -IdpType <AuthenticationMode> [<CommonParameters>]
```

## DESCRIPTION
Claim mappings are used to map claims provided by an identity provider to directory attributes in the Active Directory, so that users can be identified and authenticated by the system.

By default, Access Manager automatically maps the 'upn', 'sid' and 'onprem_sid' claims to their respective AD attributes.

This cmdlet returns the user-provided claim mappings for the specified identity provider.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AmsIdpClaimMapping -IdpType oidc
```

This example gets the claim mappings for an OpenID Connect identity provider

## PARAMETERS

### -IdpType
The type of identity provider that this claim mapping applies to.
Value can be 'oidc' or 'wsfed'

```yaml
Type: AuthenticationMode
Parameter Sets: (All)
Aliases:
Accepted values: wsfed, oidc

Required: True
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

### Lithnet.AccessManager.PowerShell.ClaimMappingPSObject

## NOTES

## RELATED LINKS
