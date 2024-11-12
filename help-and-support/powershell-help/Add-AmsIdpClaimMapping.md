---
external help file: Lithnet.AccessManager.PowerShell.dll-Help.xml
Module Name: LithnetAccessManager
online version:
schema: 2.0.0
---

# Add-AmsIdpClaimMapping

## SYNOPSIS
Adds a claim mapping for an identity provider

## SYNTAX

```
Add-AmsIdpClaimMapping -IdpType <AuthenticationMode> -ClaimName <String> -ClaimValueType <ClaimValueType>
 [-DirectoryAttributeName <String>] [<CommonParameters>]
```

## DESCRIPTION
Claim mappings are used to map claims provided by an identity provider to directory attributes in the Active Directory, so that users can be identified and authenticated by the system.

By default, Access Manager automatically maps the 'upn', 'sid' and 'onprem_sid' claims to their respective AD attributes. If you need to provide alternative mappings, you can use this cmdlet to add them.

Note, that adding a claim mapping overrides the default mappings.

Claim mappings are only supported for OpenID Connect and WS-Federation identity providers.

## EXAMPLES

### Example 1
```powershell
PS C:\> Add-AmsIdpClaimMapping -IdpType oidc -ClaimName 'alt_upn' -ClaimValueType Upn
```

This example adds a claim mapping for the 'alt_upn' claim, which is a UPN claim, for an OpenID Connect identity provider

### Example 2
```powershell
PS C:\> Add-AmsIdpClaimMapping -IdpType oidc -ClaimName 'email' -ClaimValueType Custom -DirectoryAttributeName 'mail'
```

This example adds a claim mapping for the 'email' claim, which is a custom claim, for an OpenID Connect identity provider. The claim value will be matched against the 'mail' attribute in the directory

### Example 3
```powershell
PS C:\> Add-AmsIdpClaimMapping -IdpType wsfed -ClaimName 'login_name' -ClaimValueType Upn
```

This example adds a claim mapping for the 'login_name' claim, which is a UPN claim, for a WS-Federation identity provider

## PARAMETERS

### -ClaimName
The name of the claim provided by the identity provider

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClaimValueType
The type of data contained within the claim. This can be 'Upn', 'SamAccountName', 'Sid' or 'Custom'. Custom is used to match the claim value against a specific directory attribute

```yaml
Type: ClaimValueType
Parameter Sets: (All)
Aliases:
Accepted values: Upn, SamAccountName, Sid, Custom

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryAttributeName
The name of the custom directory attribute used to match on the provided claim value.
Used only when ClaimValueType is set to 'custom'

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
