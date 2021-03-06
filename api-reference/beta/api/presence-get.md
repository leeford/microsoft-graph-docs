---
title: "Get presence"
description: "Get a user's presence information."
author: "VinodRavichandran"
localization_priority: Normal
doc_type: apiPageType
ms.prod: "cloud-communications"
---

# Get presence

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a user's [presence](../resources/presence.md) information.

## Permissions
One of the following permissions is required to call these APIs. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type | Permissions (from least to most privileged)                  |
| :-------------- | :----------------------------------------------------------- |
| Delegated (work or school account)     | Presence.Read, Presence.Read.All                         |
| Delegated (personal Microsoft account) | Not Supported.                         |
| Application                            | Not Supported.                                  |

## HTTP Requests
<!-- { "blockType": "ignored" } -->
```http
GET /me/presence
GET /users/{id}/presence
```

## Request Headers
| Name          | Description               |
|:--------------|:--------------------------|
| Authorization | Bearer {token}. Required. |


## Request body

Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a [presence](../resources/presence.md) object in the response body.

## Examples

### Example 1: Get your own presence information

The following example shows how to get your own presence information. This operation requires the Presence.Read permission.

#### Request

<!-- {
  "blockType": "request",
  "name": "get-your-presence"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/me/presence
```

#### Response

<!-- {
  "blockType": "response",
  "name": "get-your-presence",
  "@odata.type": "microsoft.graph.presence",
  "truncated":"true"
} -->
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 1574

{  
	"id": "fa8bf3dc-eca7-46b7-bad1-db199b62afc3",
	"availability": "Available",
	"activity": "Available"
}
```

### Example 2: Get the presence information of another user

The following example shows how to get the presence information for another user. This operation requires the Presence.Read.All permission.

#### Request
<!-- {
  "blockType": "request",
  "name": "get-user-presence"
}-->
```http
GET https://graph.microsoft.com/beta/users/66825e03-7ef5-42da-9069-724602c31f6b/presence
```

#### Response

<!-- {
  "blockType": "response",
  "name": "get-user-presence",
  "@odata.type": "microsoft.graph.presence",
  "truncated":"true"
}-->

```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 1574

{
	"id": "66825e03-7ef5-42da-9069-724602c31f6b",
	"availability": "DoNotDisturb",
	"activity": "Presenting"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Get Presence",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
