---
title: "Create messageEvent"
description: "Create a new messageEvent object."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
localization_priority: Normal
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://msgo.azurewebsites.net/add/document/guidelines/metadata.html#topic-level-metadata)**"
doc_type: apiPageType
---

# Create messageEvent
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new messageEvent object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|**TODO: Provide applicable permissions.**|
|Delegated (personal Microsoft account)|**TODO: Provide applicable permissions.**|
|Application|**TODO: Provide applicable permissions.**|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /messageRecipients/{messageRecipientsId}/events
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [messageEvent](../resources/messageevent.md) object.

The following table shows the properties that are required when you create the [messageEvent](../resources/messageevent.md).

|Property|Type|Description|
|:---|:---|:---|
|id|String|**TODO: Add Description** Inherited from [entity](../resources/entity.md)|
|dateTime|DateTimeOffset|**TODO: Add Description**|
|eventType|messageEventType|**TODO: Add Description**. Possible values are: `received`, `sent`, `delivered`, `failed`, `processingFailed`, `distributionGroupExpanded`, `submitted`, `delayed`, `redirected`, `resolved`, `dropped`, `recipientsAdded`, `malwareDetected`, `malwareDetectedInMessage`, `malwareDetectedInAttachment`, `ttZapped`, `ttDelivered`, `spamDetected`, `transportRuleTriggered`, `dlpRuleTriggered`, `journaled`, `unknownFutureValue`.|
|description|String|**TODO: Add Description**|



## Response

If successful, this method returns a `201 Created` response code and a [messageEvent](../resources/messageevent.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "create_messageevent_from_messageevents"
}
-->
``` http
POST https://graph.microsoft.com/beta/messageRecipients/{messageRecipientsId}/events
Content-Type: application/json
Content-length: 145

{
  "@odata.type": "#microsoft.graph.messageEvent",
  "dateTime": "String (timestamp)",
  "eventType": "String",
  "description": "String"
}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.messageEvent"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.messageEvent",
  "id": "bb1a6d63-6d63-bb1a-636d-1abb636d1abb",
  "dateTime": "String (timestamp)",
  "eventType": "String",
  "description": "String"
}
```
