---
Module Name: PnP.PowerShell
title: Invoke-PnPGraphMethod
schema: 2.0.0
applicable: SharePoint Online
external help file: PnP.PowerShell.dll-Help.xml
online version: https://pnp.github.io/powershell/cmdlets/Invoke-PnPGraphMethod.html
---

# Invoke-PnPGraphMethod

## SYNOPSIS
Invokes a REST request towards the Microsoft Graph API

## SYNTAX

```powershell
Invoke-PnPGraphMethod -Url <String>
                      [-AdditionalHeaders <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
                      [[-Method] <HttpRequestMethod>] 
                      [-Content <Object>] 
                      [-ContentType <String>] 
                      [-ConsistencyLevelEventual] 
                      [-Raw]
                      [-All] 
                      [-Connection <PnPConnection>]
                      [<CommonParameters>]
```

## DESCRIPTION
Invokes a REST request towards the Microsoft Graph API

## EXAMPLES

### Example 1
```powershell
Invoke-PnPGraphMethod -Url "groups?`$filter=startsWith(displayName,'ZZ')&`$select=displayName"
Invoke-PnPGraphMethod -Url 'groups/{id}?`$select=hideFromOutlookClients'
```

Execute a GET request to get groups by filter and select.

### Example 2
```powershell
Invoke-PnPGraphMethod -Url "groups/{id}" -Method Delete
```

Delete the group with the specified id.

### Example 3
```powershell
Invoke-PnPGraphMethod -Url "groups/{id}" -Method Patch -Content @{ displayName = "NewName" }
```

Set the new displayName of the group with a Patch request.

### Example 4
```powershell
Invoke-PnPGraphMethod -Url "v1.0/users?$filter=accountEnabled ne true&$count=true" -Method Get -ConsistencyLevelEventual
```

Get users with advanced query capabilities. Use of -ConsistencyLevelEventual.

## PARAMETERS

### -AdditionalHeaders
Additional request headers

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -All
Retrieve all pages of results. This will loop through all @odata.nextLink. This flag will only be respected if the request is a GET request.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Connection
Optional connection to be used by the cmdlet.
Retrieve the value for this parameter by either specifying -ReturnConnection on Connect-PnPOnline or by executing Get-PnPConnection.

```yaml
Type: PnPConnection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsistencyLevelEventual
Set the ConsistencyLevel header to eventual for advanced query capabilities on Azure AD directory objects


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Content
A string or object to send

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentType
The content type of the object to send. Defaults to 'application/json'.

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

### -Method
The HTTP method to execute. Defaults to GET.

```yaml
Type: HttpRequestMethod
Parameter Sets: (All)
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Raw
If specified the returned data will not be converted to an object but returned as a JSON string.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Url
The Graph endpoint to invoke.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## RELATED LINKS

[Microsoft 365 Patterns and Practices](https://aka.ms/m365pnp)
