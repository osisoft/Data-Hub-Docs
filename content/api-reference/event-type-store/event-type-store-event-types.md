---
uid: event-type-store-event-types

---

# Event Types

## `List Event Types`

<a id="opIdEventTypes_List Event Types"></a>

Returns an array of EventTypes in a given namespace and the version ETag in the HTTP response header. The If-Match and If-None-Match headers are supported.

<h3>Request</h3>

```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes
?skip={skip}&count={count}&filter={filter}&includeDeleted={includeDeleted}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/>Parameter representing the zero-based offset of the first object to retrieve.  If unspecified, a default value of 0 is used.<br/><br/>`[optional] integer count`
<br/>Parameter representing the maximum number of objects to retrieve. If unspecified, a default value of 100 is used.<br/><br/>`[optional] string filter`
<br/>Parameter representing the condition for results to be filtered by. If unspecified, results are not filtered.<br/><br/>`[optional] boolean includeDeleted`
<br/>Parameter indicating whether to include deleted EventType properties. If unspecified, a default value of false is used.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[EventType](#schemaeventtype)[]|Success.|
|304|None|Not modified.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|412|[AdhErrorResponse](#schemaadherrorresponse)|Precondition failed.|

<h4>Example response body</h4>

> 200 Response

```json
[
  {
    "Id": "SimpleEvent",
    "Name": "SimpleEvent",
    "GraphQLName": "SimpleEvent",
    "State": "Active",
    "Properties": [
      {
        "PropertyTypeCode": "DateTime",
        "Id": "eventStartTime",
        "Name": "eventStartTime",
        "GraphQLName": "eventStartTime",
        "Flags": "None",
        "State": "Active",
        "Description": "The start time of the event."
      },
      {
        "PropertyTypeCode": "DateTime",
        "Id": "eventEndTime",
        "Name": "eventEndTime",
        "GraphQLName": "eventEndTime",
        "Flags": "None",
        "State": "Active",
        "Description": "The end time of the event."
      },
      {
        "PropertyTypeCode": "TimeSpan",
        "Id": "eventDuration",
        "Name": "eventDuration",
        "GraphQLName": "eventDuration",
        "Flags": "None",
        "State": "Active",
        "Description": "The duration of the event."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "id",
        "Name": "id",
        "GraphQLName": "id",
        "Flags": "None",
        "State": "Active",
        "Description": "A unique identifier for the event instance."
      },
      {
        "PropertyTypeCode": "DateTime",
        "Id": "modifiedDate",
        "Name": "modifiedDate",
        "GraphQLName": "modifiedDate",
        "Flags": "None",
        "State": "Active",
        "Description": "The last modified date and time of the event."
      },
      {
        "PropertyTypeCode": "DateTime",
        "Id": "createdDate",
        "Name": "createdDate",
        "GraphQLName": "createdDate",
        "Flags": "None",
        "State": "Active",
        "Description": "The date and time at which the event was created."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "createdByUser",
        "Name": "createdByUser",
        "GraphQLName": "createdByUser",
        "Flags": "None",
        "State": "Active",
        "Description": "The identity of the user that created the event."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "eventType",
        "Name": "eventType",
        "GraphQLName": "eventType",
        "Flags": "None",
        "State": "Active",
        "Description": "The type of the event."
      },
      {
        "PropertyTypeCode": "Enumeration",
        "Id": "eventState",
        "Name": "eventState",
        "GraphQLName": "eventState",
        "Flags": "None",
        "State": "Active",
        "PropertyTypeId": "EventState",
        "RemoteReferenceName": "EventState",
        "Description": "The state of the event."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "authorizationTags",
        "Name": "authorizationTags",
        "GraphQLName": "authorizationTags",
        "Flags": "IsCollection",
        "State": "Active",
        "Description": "The list of tags used to authorize access to the event."
      }
    ],
    "Version": 1,
    "CreatedDate": "0001-01-01T00:00:00Z",
    "ModifiedDate": "0001-01-01T00:00:00Z",
    "DefaultAuthorizationTag": "BaseAuthorizationTag",
    "Description": "This is a simple event type"
  }
]
```

> 400 Response ([AdhErrorResponse](#schemaadherrorresponse))

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---

## `Create Event Type With Server Generated Id`

<a id="opIdEventTypes_Create Event Type With Server Generated Id"></a>

Creates a new EventType. Response includes ETag header.

<h3>Request</h3>

```text 
POST /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

<h4>Request Body</h4>

An EventType.<br/>

```json
{
  "Name": "SimpleEvent",
  "Properties": [
    {
      "Id": "eventStartTime",
      "PropertyTypeCode": "DateTime"
    },
    {
      "Id": "eventEndTime",
      "PropertyTypeCode": "DateTime"
    },
    {
      "Id": "eventDuration",
      "PropertyTypeCode": "TimeSpan"
    }
  ]
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[EventType](#schemaeventtype)|Created.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|409|[AdhErrorResponse](#schemaadherrorresponse)|Conflict.|

<h4>Example response body</h4>

> 201 Response

```json
{
  "Id": "6B29FC40-CA47-1067-B31D-00DD010662DA",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 400 Response ([AdhErrorResponse](#schemaadherrorresponse))

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---

## `Get Event Type By Id`

<a id="opIdEventTypes_Get Event Type By Id"></a>

Returns the specified EventType and the version ETag in the HTTP response header. The If-Match and If-None-Match headers are supported.

<h3>Request</h3>

```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}
?includeDeleted={includeDeleted}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>`boolean includeDeleted`
<br/>Parameter indicating whether to include deleted EventType properties. If unspecified, a default value of false is used.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[EventType](#schemaeventtype)|Success.|
|304|None|Not modified.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|
|412|[AdhErrorResponse](#schemaadherrorresponse)|Precondition failed.|

<h4>Example response body</h4>

> 200 Response

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 400 Response ([AdhErrorResponse](#schemaadherrorresponse))

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---

## `Get Or Create Event Type`

<a id="opIdEventTypes_Get Or Create Event Type"></a>

Creates a new EventType or returns the current one if the body is equivalent to what is stored. Response includes ETag header.

<h3>Request</h3>

```text 
POST /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h4>Request Body</h4>

An EventType.<br/>

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "Properties": [
    {
      "Id": "eventStartTime",
      "PropertyTypeCode": "DateTime"
    },
    {
      "Id": "eventEndTime",
      "PropertyTypeCode": "DateTime"
    },
    {
      "Id": "eventDuration",
      "PropertyTypeCode": "TimeSpan"
    }
  ]
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[EventType](#schemaeventtype)|Success.|
|201|[EventType](#schemaeventtype)|Created.|
|302|None|Found.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|409|[AdhErrorResponse](#schemaadherrorresponse)|Conflict|

<h4>Example response body</h4>

> 200 Response

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 201 Response

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 400 Response ([AdhErrorResponse](#schemaadherrorresponse))

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---

## `Create Or Update Event Type`

<a id="opIdEventTypes_Create Or Update Event Type"></a>

Creates a new EventType or updates an existing and adds its Etag in the HTTP response header. Updating the state of the properties to deleted is supported through this route. Hard Delete of the type however must be done with through the DELETE endpoint. The If-Match header is supported.

<h3>Request</h3>

```text 
PUT /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h4>Request Body</h4>

An EventType.<br/>

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "Properties": [
    {
      "Id": "eventStartTime",
      "PropertyTypeCode": "DateTime"
    },
    {
      "Id": "eventEndTime",
      "PropertyTypeCode": "DateTime"
    },
    {
      "Id": "eventDuration",
      "PropertyTypeCode": "TimeSpan"
    }
  ]
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[EventType](#schemaeventtype)|Success.|
|201|[EventType](#schemaeventtype)|Created.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|409|[AdhErrorResponse](#schemaadherrorresponse)|Conflict.|
|412|[AdhErrorResponse](#schemaadherrorresponse)|Precondition failed.|

<h4>Example response body</h4>

> 200 Response

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 201 Response

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 400 Response ([AdhErrorResponse](#schemaadherrorresponse))

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---

## `Delete Event Type By Id`

<a id="opIdEventTypes_Delete Event Type By Id"></a>

Deletes the EventType.

<h3>Request</h3>

```text 
DELETE /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Deleted.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|
|409|[AdhErrorResponse](#schemaadherrorresponse)|Conflict.|

---

## `Bulk Create Event Type`

<a id="opIdEventTypes_Bulk Create Event Type"></a>

Creates multiple new EventType and returns a list of any errors along with the created objects. Response includes ETag header.

<h3>Request</h3>

```text 
POST /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/Bulk/EventTypes
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

<h4>Request Body</h4>

A list of EventType objects.<br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[EventType](#schemaeventtype)|Success.|
|207|[MultiStatusResultOfEventTypeAndAdhErrorResponse](#schemamultistatusresultofeventtypeandadherrorresponse)|Partial.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|409|[AdhErrorResponse](#schemaadherrorresponse)|Conflict.|

<h4>Example response body</h4>

> 200 Response

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}
```

> 207 Response ([MultiStatusResultOfEventTypeAndAdhErrorResponse](#schemamultistatusresultofeventtypeandadherrorresponse))

```json
{
  "Reason": "string",
  "Error": "string",
  "OperationId": "string",
  "Data": [
    {
      "Id": "SimpleEvent",
      "Name": "SimpleEvent",
      "GraphQLName": "SimpleEvent",
      "State": "Active",
      "Properties": [
        {
          "PropertyTypeCode": "DateTime",
          "Id": "eventStartTime",
          "Name": "eventStartTime",
          "GraphQLName": "eventStartTime",
          "Flags": "None",
          "State": "Active",
          "Description": "The start time of the event."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "eventEndTime",
          "Name": "eventEndTime",
          "GraphQLName": "eventEndTime",
          "Flags": "None",
          "State": "Active",
          "Description": "The end time of the event."
        },
        {
          "PropertyTypeCode": "TimeSpan",
          "Id": "eventDuration",
          "Name": "eventDuration",
          "GraphQLName": "eventDuration",
          "Flags": "None",
          "State": "Active",
          "Description": "The duration of the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "id",
          "Name": "id",
          "GraphQLName": "id",
          "Flags": "None",
          "State": "Active",
          "Description": "A unique identifier for the event instance."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "modifiedDate",
          "Name": "modifiedDate",
          "GraphQLName": "modifiedDate",
          "Flags": "None",
          "State": "Active",
          "Description": "The last modified date and time of the event."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "createdDate",
          "Name": "createdDate",
          "GraphQLName": "createdDate",
          "Flags": "None",
          "State": "Active",
          "Description": "The date and time at which the event was created."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "createdByUser",
          "Name": "createdByUser",
          "GraphQLName": "createdByUser",
          "Flags": "None",
          "State": "Active",
          "Description": "The identity of the user that created the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "eventType",
          "Name": "eventType",
          "GraphQLName": "eventType",
          "Flags": "None",
          "State": "Active",
          "Description": "The type of the event."
        },
        {
          "PropertyTypeCode": "Enumeration",
          "Id": "eventState",
          "Name": "eventState",
          "GraphQLName": "eventState",
          "Flags": "None",
          "State": "Active",
          "PropertyTypeId": "EventState",
          "RemoteReferenceName": "EventState",
          "Description": "The state of the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "authorizationTags",
          "Name": "authorizationTags",
          "GraphQLName": "authorizationTags",
          "Flags": "IsCollection",
          "State": "Active",
          "Description": "The list of tags used to authorize access to the event."
        }
      ],
      "Version": 1,
      "CreatedDate": "0001-01-01T00:00:00Z",
      "ModifiedDate": "0001-01-01T00:00:00Z",
      "DefaultAuthorizationTag": "BaseAuthorizationTag",
      "Description": "This is a simple event type"
    }
  ],
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "property1": null,
      "property2": null
    }
  ]
}
```

---

## `Bulk Delete Event Type`

<a id="opIdEventTypes_Bulk Delete Event Type"></a>

Deletes multiple EventTypes and returns an Ok if successful. In the case where a deletion is invalid, it will be added to a child errors list while the ones that were successful will be returned in the data.

<h3>Request</h3>

```text 
DELETE /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/Bulk/EventTypes
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

<h4>Request Body</h4>

A list of EventType object ids.<br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[EventType](#schemaeventtype)[]|Success.|
|207|[MultiStatusResultOfEventTypeAndAdhErrorResponse](#schemamultistatusresultofeventtypeandadherrorresponse)|Partial.|
|400|[AdhErrorResponse](#schemaadherrorresponse)|Missing or invalid inputs.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|409|[AdhErrorResponse](#schemaadherrorresponse)|Conflict.|

<h4>Example response body</h4>

> 200 Response

```json
[
  {
    "Id": "SimpleEvent",
    "Name": "SimpleEvent",
    "GraphQLName": "SimpleEvent",
    "State": "Active",
    "Properties": [
      {
        "PropertyTypeCode": "DateTime",
        "Id": "eventStartTime",
        "Name": "eventStartTime",
        "GraphQLName": "eventStartTime",
        "Flags": "None",
        "State": "Active",
        "Description": "The start time of the event."
      },
      {
        "PropertyTypeCode": "DateTime",
        "Id": "eventEndTime",
        "Name": "eventEndTime",
        "GraphQLName": "eventEndTime",
        "Flags": "None",
        "State": "Active",
        "Description": "The end time of the event."
      },
      {
        "PropertyTypeCode": "TimeSpan",
        "Id": "eventDuration",
        "Name": "eventDuration",
        "GraphQLName": "eventDuration",
        "Flags": "None",
        "State": "Active",
        "Description": "The duration of the event."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "id",
        "Name": "id",
        "GraphQLName": "id",
        "Flags": "None",
        "State": "Active",
        "Description": "A unique identifier for the event instance."
      },
      {
        "PropertyTypeCode": "DateTime",
        "Id": "modifiedDate",
        "Name": "modifiedDate",
        "GraphQLName": "modifiedDate",
        "Flags": "None",
        "State": "Active",
        "Description": "The last modified date and time of the event."
      },
      {
        "PropertyTypeCode": "DateTime",
        "Id": "createdDate",
        "Name": "createdDate",
        "GraphQLName": "createdDate",
        "Flags": "None",
        "State": "Active",
        "Description": "The date and time at which the event was created."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "createdByUser",
        "Name": "createdByUser",
        "GraphQLName": "createdByUser",
        "Flags": "None",
        "State": "Active",
        "Description": "The identity of the user that created the event."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "eventType",
        "Name": "eventType",
        "GraphQLName": "eventType",
        "Flags": "None",
        "State": "Active",
        "Description": "The type of the event."
      },
      {
        "PropertyTypeCode": "Enumeration",
        "Id": "eventState",
        "Name": "eventState",
        "GraphQLName": "eventState",
        "Flags": "None",
        "State": "Active",
        "PropertyTypeId": "EventState",
        "RemoteReferenceName": "EventState",
        "Description": "The state of the event."
      },
      {
        "PropertyTypeCode": "String",
        "Id": "authorizationTags",
        "Name": "authorizationTags",
        "GraphQLName": "authorizationTags",
        "Flags": "IsCollection",
        "State": "Active",
        "Description": "The list of tags used to authorize access to the event."
      }
    ],
    "Version": 1,
    "CreatedDate": "0001-01-01T00:00:00Z",
    "ModifiedDate": "0001-01-01T00:00:00Z",
    "DefaultAuthorizationTag": "BaseAuthorizationTag",
    "Description": "This is a simple event type"
  }
]
```

> 207 Response ([MultiStatusResultOfEventTypeAndAdhErrorResponse](#schemamultistatusresultofeventtypeandadherrorresponse))

```json
{
  "Reason": "string",
  "Error": "string",
  "OperationId": "string",
  "Data": [
    {
      "Id": "SimpleEvent",
      "Name": "SimpleEvent",
      "GraphQLName": "SimpleEvent",
      "State": "Active",
      "Properties": [
        {
          "PropertyTypeCode": "DateTime",
          "Id": "eventStartTime",
          "Name": "eventStartTime",
          "GraphQLName": "eventStartTime",
          "Flags": "None",
          "State": "Active",
          "Description": "The start time of the event."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "eventEndTime",
          "Name": "eventEndTime",
          "GraphQLName": "eventEndTime",
          "Flags": "None",
          "State": "Active",
          "Description": "The end time of the event."
        },
        {
          "PropertyTypeCode": "TimeSpan",
          "Id": "eventDuration",
          "Name": "eventDuration",
          "GraphQLName": "eventDuration",
          "Flags": "None",
          "State": "Active",
          "Description": "The duration of the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "id",
          "Name": "id",
          "GraphQLName": "id",
          "Flags": "None",
          "State": "Active",
          "Description": "A unique identifier for the event instance."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "modifiedDate",
          "Name": "modifiedDate",
          "GraphQLName": "modifiedDate",
          "Flags": "None",
          "State": "Active",
          "Description": "The last modified date and time of the event."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "createdDate",
          "Name": "createdDate",
          "GraphQLName": "createdDate",
          "Flags": "None",
          "State": "Active",
          "Description": "The date and time at which the event was created."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "createdByUser",
          "Name": "createdByUser",
          "GraphQLName": "createdByUser",
          "Flags": "None",
          "State": "Active",
          "Description": "The identity of the user that created the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "eventType",
          "Name": "eventType",
          "GraphQLName": "eventType",
          "Flags": "None",
          "State": "Active",
          "Description": "The type of the event."
        },
        {
          "PropertyTypeCode": "Enumeration",
          "Id": "eventState",
          "Name": "eventState",
          "GraphQLName": "eventState",
          "Flags": "None",
          "State": "Active",
          "PropertyTypeId": "EventState",
          "RemoteReferenceName": "EventState",
          "Description": "The state of the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "authorizationTags",
          "Name": "authorizationTags",
          "GraphQLName": "authorizationTags",
          "Flags": "IsCollection",
          "State": "Active",
          "Description": "The list of tags used to authorize access to the event."
        }
      ],
      "Version": 1,
      "CreatedDate": "0001-01-01T00:00:00Z",
      "ModifiedDate": "0001-01-01T00:00:00Z",
      "DefaultAuthorizationTag": "BaseAuthorizationTag",
      "Description": "This is a simple event type"
    }
  ],
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "property1": null,
      "property2": null
    }
  ]
}
```

---

## `Get Event Type Acl By Id`

<a id="opIdEventTypes_Get Event Type Acl By Id"></a>

Returns the `AccessControlList` for the specified EventType.

<h3>Request</h3>

```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}/AccessControl
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|Success.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|

<h4>Example response body</h4>

> 200 Response ([AccessControlList](#schemaaccesscontrollist))

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": 1,
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

---

## `Update Event Type Acl By Id`

<a id="opIdEventTypes_Update Event Type Acl By Id"></a>

Updates and returns the `AccessControlList` for the specified EventType.

<h3>Request</h3>

```text 
PUT /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}/AccessControl
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h4>Request Body</h4>

An AccessControlList.<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": 3,
        "ObjectId": "11111111-1111-1111-1111-111111111111"
      },
      "AccessType": 0,
      "AccessRights": 3
    },
    {
      "Trustee": {
        "Type": 3,
        "ObjectId": "22222222-2222-2222-1111-111111111111"
      },
      "AccessType": 0,
      "AccessRights": 15
    }
  ]
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|Success.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|

<h4>Example response body</h4>

> 200 Response ([AccessControlList](#schemaaccesscontrollist))

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": 1,
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

---

## `Get Event Type Owner By Id`

<a id="opIdEventTypes_Get Event Type Owner By Id"></a>

Returns the `Trustee` for the specified EventType.

<h3>Request</h3>

```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}/Owner
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|Success.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|

<h4>Example response body</h4>

> 200 Response ([Trustee](#schematrustee))

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

---

## `Update Event Type Owner By Id`

<a id="opIdEventTypes_Update Event Type Owner By Id"></a>

Updates and returns the `Trustee` for the specified EventType.

<h3>Request</h3>

```text 
PUT /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}/Owner
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h4>Request Body</h4>

A Trustee.<br/>

```json
{
  "Type": 1,
  "TenantId": "55555555-5555-5555-5555-555555555555",
  "ObjectId": "44444444-4444-4444-4444-444444444444"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|Success.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|

<h4>Example response body</h4>

> 200 Response ([Trustee](#schematrustee))

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

---

## `List Event Type Access Rights By Id`

<a id="opIdEventTypes_List Event Type Access Rights By Id"></a>

Returns a list of `CommonAccessRights` for the specified EventType.

<h3>Request</h3>

```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/EventTypes/{id}/AccessRights
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/>The id of the EventType.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Success.|
|403|[AdhErrorResponse](#schemaadherrorresponse)|Forbidden.|
|404|[AdhErrorResponse](#schemaadherrorresponse)|EventType not found.|

---
## Definitions

### EventType

<a id="schemaeventtype"></a>
<a id="schema_EventType"></a>
<a id="tocSeventtype"></a>
<a id="tocseventtype"></a>

Represents an EventType object.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|The name of this object|
|GraphQLName|string|false|true|The name of this object as it appears in GraphQL|
|Version|int32|false|false|The current version number of this object|
|Id|string|false|true|The id which is used in lookup|
|State|[LifeCycleState](#schemalifecyclestate)|false|false|The lifecycle state of this object|
|CreatedDate|date-time|false|true|Date this object was created|
|ModifiedDate|date-time|false|true|The last time this object was modified|
|Description|string|false|true|Description of what this object is|
|Properties|[[TypeProperty](#schematypeproperty)]|false|true|List of TypeProperty associated with this EventType|
|DefaultAuthorizationTag|string|false|true|The authorization tag that will be added to all instances of nodes based on the type|

```json
{
  "Id": "SimpleEvent",
  "Name": "SimpleEvent",
  "GraphQLName": "SimpleEvent",
  "State": "Active",
  "Properties": [
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventStartTime",
      "Name": "eventStartTime",
      "GraphQLName": "eventStartTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The start time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "eventEndTime",
      "Name": "eventEndTime",
      "GraphQLName": "eventEndTime",
      "Flags": "None",
      "State": "Active",
      "Description": "The end time of the event."
    },
    {
      "PropertyTypeCode": "TimeSpan",
      "Id": "eventDuration",
      "Name": "eventDuration",
      "GraphQLName": "eventDuration",
      "Flags": "None",
      "State": "Active",
      "Description": "The duration of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "id",
      "Name": "id",
      "GraphQLName": "id",
      "Flags": "None",
      "State": "Active",
      "Description": "A unique identifier for the event instance."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "modifiedDate",
      "Name": "modifiedDate",
      "GraphQLName": "modifiedDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The last modified date and time of the event."
    },
    {
      "PropertyTypeCode": "DateTime",
      "Id": "createdDate",
      "Name": "createdDate",
      "GraphQLName": "createdDate",
      "Flags": "None",
      "State": "Active",
      "Description": "The date and time at which the event was created."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "createdByUser",
      "Name": "createdByUser",
      "GraphQLName": "createdByUser",
      "Flags": "None",
      "State": "Active",
      "Description": "The identity of the user that created the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "eventType",
      "Name": "eventType",
      "GraphQLName": "eventType",
      "Flags": "None",
      "State": "Active",
      "Description": "The type of the event."
    },
    {
      "PropertyTypeCode": "Enumeration",
      "Id": "eventState",
      "Name": "eventState",
      "GraphQLName": "eventState",
      "Flags": "None",
      "State": "Active",
      "PropertyTypeId": "EventState",
      "RemoteReferenceName": "EventState",
      "Description": "The state of the event."
    },
    {
      "PropertyTypeCode": "String",
      "Id": "authorizationTags",
      "Name": "authorizationTags",
      "GraphQLName": "authorizationTags",
      "Flags": "IsCollection",
      "State": "Active",
      "Description": "The list of tags used to authorize access to the event."
    }
  ],
  "Version": 1,
  "CreatedDate": "0001-01-01T00:00:00Z",
  "ModifiedDate": "0001-01-01T00:00:00Z",
  "DefaultAuthorizationTag": "BaseAuthorizationTag",
  "Description": "This is a simple event type"
}

```

---

### LifeCycleState

<a id="schemalifecyclestate"></a>
<a id="schema_LifeCycleState"></a>
<a id="tocSlifecyclestate"></a>
<a id="tocslifecyclestate"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Active|0|
|Deprecated|1|
|Deleted|2|

---

### TypeProperty

<a id="schematypeproperty"></a>
<a id="schema_TypeProperty"></a>
<a id="tocStypeproperty"></a>
<a id="tocstypeproperty"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PropertyTypeCode|[PropertyTypeCode](#schemapropertytypecode)|false|false|Code that explains what kind of typeProperty this is|
|Id|string|false|true|The id; used in lookup|
|Name|string|false|true|The name of this TypeProperty|
|GraphQLName|string|false|true|The name of this TypeProperty as it appears in GraphQL|
|Flags|[PropertyTypeFlags](#schemapropertytypeflags)|false|false|Flag that denotes what special attributes this property has|
|State|[LifeCycleState](#schemalifecyclestate)|false|false|The lifecycle state of this TypeProperty|
|PropertyTypeId|string|false|true|The id of the type that this property points to|
|RemoteReferenceName|string|false|true|The name of the invisible property that is generated in GraphQL type schema if the ReverseLookup flag is set that points to this TypeProperty|
|Description|string|false|true|Description of what this TypeProperty is|
|Uom|string|false|true|The unit of measure for the type property. This property is only present/valid for numeric PropertyTypeCodes|

```json
{
  "PropertyTypeCode": 0,
  "Id": "string",
  "Name": "string",
  "GraphQLName": "string",
  "Flags": 0,
  "State": 0,
  "PropertyTypeId": "string",
  "RemoteReferenceName": "string",
  "Description": "string",
  "Uom": "string"
}

```

---

### PropertyTypeCode

<a id="schemapropertytypecode"></a>
<a id="schema_PropertyTypeCode"></a>
<a id="tocSpropertytypecode"></a>
<a id="tocspropertytypecode"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Empty|0|
|Boolean|3|
|Int32|9|
|Int64|11|
|Double|14|
|DateTime|16|
|String|18|
|TimeSpan|21|
|Event|10000|
|Enumeration|10001|
|ReferenceData|10002|
|Asset|10003|

---

### PropertyTypeFlags

<a id="schemapropertytypeflags"></a>
<a id="schema_PropertyTypeFlags"></a>
<a id="tocSpropertytypeflags"></a>
<a id="tocspropertytypeflags"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|None|0|
|NoReverseLookup|1|
|Indexed|2|
|Required|4|
|IsCollection|8|
|NoUom|16|
|NoAggregation|32|

---

### AdhErrorResponse

<a id="schemaadherrorresponse"></a>
<a id="schema_AdhErrorResponse"></a>
<a id="tocSadherrorresponse"></a>
<a id="tocsadherrorresponse"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|An optional unique string used to identify an operation|
|Error|string|false|true|Description of the error|
|Reason|string|false|true|Short blurb on why the error occured|
|Resolution|string|false|true|Short blurb on how to fix the error|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}

```

---

### MultiStatusResultOfEventTypeAndAdhErrorResponse

<a id="schemamultistatusresultofeventtypeandadherrorresponse"></a>
<a id="schema_MultiStatusResultOfEventTypeAndAdhErrorResponse"></a>
<a id="tocSmultistatusresultofeventtypeandadherrorresponse"></a>
<a id="tocsmultistatusresultofeventtypeandadherrorresponse"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Reason|string|false|false|Short blurb on why the error occured|
|Error|string|false|false|Description of the error|
|OperationId|string|false|false|An optional unique string used to identify an operation|
|Data|[[EventType](#schemaeventtype)]|false|false|List of data returned from the multi-calls|
|ChildErrors|[[AdhErrorResponse](#schemaadherrorresponse)]|false|false|List of errors from all the multi-calls|

```json
{
  "Reason": "string",
  "Error": "string",
  "OperationId": "string",
  "Data": [
    {
      "Id": "SimpleEvent",
      "Name": "SimpleEvent",
      "GraphQLName": "SimpleEvent",
      "State": "Active",
      "Properties": [
        {
          "PropertyTypeCode": "DateTime",
          "Id": "eventStartTime",
          "Name": "eventStartTime",
          "GraphQLName": "eventStartTime",
          "Flags": "None",
          "State": "Active",
          "Description": "The start time of the event."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "eventEndTime",
          "Name": "eventEndTime",
          "GraphQLName": "eventEndTime",
          "Flags": "None",
          "State": "Active",
          "Description": "The end time of the event."
        },
        {
          "PropertyTypeCode": "TimeSpan",
          "Id": "eventDuration",
          "Name": "eventDuration",
          "GraphQLName": "eventDuration",
          "Flags": "None",
          "State": "Active",
          "Description": "The duration of the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "id",
          "Name": "id",
          "GraphQLName": "id",
          "Flags": "None",
          "State": "Active",
          "Description": "A unique identifier for the event instance."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "modifiedDate",
          "Name": "modifiedDate",
          "GraphQLName": "modifiedDate",
          "Flags": "None",
          "State": "Active",
          "Description": "The last modified date and time of the event."
        },
        {
          "PropertyTypeCode": "DateTime",
          "Id": "createdDate",
          "Name": "createdDate",
          "GraphQLName": "createdDate",
          "Flags": "None",
          "State": "Active",
          "Description": "The date and time at which the event was created."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "createdByUser",
          "Name": "createdByUser",
          "GraphQLName": "createdByUser",
          "Flags": "None",
          "State": "Active",
          "Description": "The identity of the user that created the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "eventType",
          "Name": "eventType",
          "GraphQLName": "eventType",
          "Flags": "None",
          "State": "Active",
          "Description": "The type of the event."
        },
        {
          "PropertyTypeCode": "Enumeration",
          "Id": "eventState",
          "Name": "eventState",
          "GraphQLName": "eventState",
          "Flags": "None",
          "State": "Active",
          "PropertyTypeId": "EventState",
          "RemoteReferenceName": "EventState",
          "Description": "The state of the event."
        },
        {
          "PropertyTypeCode": "String",
          "Id": "authorizationTags",
          "Name": "authorizationTags",
          "GraphQLName": "authorizationTags",
          "Flags": "IsCollection",
          "State": "Active",
          "Description": "The list of tags used to authorize access to the event."
        }
      ],
      "Version": 1,
      "CreatedDate": "0001-01-01T00:00:00Z",
      "ModifiedDate": "0001-01-01T00:00:00Z",
      "DefaultAuthorizationTag": "BaseAuthorizationTag",
      "Description": "This is a simple event type"
    }
  ],
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "property1": null,
      "property2": null
    }
  ]
}

```

---

### AccessControlList

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleTrusteeAccessControlEntries|[[AccessControlEntry](#schemaaccesscontrolentry)]|false|true|None|

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": 1,
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}

```

---

### AccessControlEntry

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Trustee|[Trustee](#schematrustee)|false|true|None|
|AccessType|[AccessType](#schemaaccesstype)|false|false|None|
|AccessRights|int64|false|false|None|

```json
{
  "Trustee": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessType": 0,
  "AccessRights": 0
}

```

---

### Trustee

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[TrusteeType](#schematrusteetype)|false|false|None|
|ObjectId|string|false|true|None|
|TenantId|string|false|true|None|

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}

```

---

### TrusteeType

<a id="schematrusteetype"></a>
<a id="schema_TrusteeType"></a>
<a id="tocStrusteetype"></a>
<a id="tocstrusteetype"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|User|1|
|Client|2|
|Role|3|

---

### AccessType

<a id="schemaaccesstype"></a>
<a id="schema_AccessType"></a>
<a id="tocSaccesstype"></a>
<a id="tocsaccesstype"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Allowed|0|
|Denied|1|

---

