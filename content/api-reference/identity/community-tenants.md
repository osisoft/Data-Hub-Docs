---
uid: ""

---

# Community Tenants
APIs for retrieving, updating and removing community tenant information

## `Update Community Tenant Info`

<a id="opIdCommunityTenants_Update Community Tenant Info"></a>

Updates the state of a community tenant. The state can be activated or paused. Also it updates preferred region id and contact email.

<h3>Request</h3>

```text 
PUT /api/v1-preview/communities/{communityId}/tenants/{tenantId}
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>Tenant identifier of the `CommunityTenant` in the community to update.<br/><br/>

<h4>Request Body</h4>

UpdateCommunityTenantInput object that contains the attributes to use for the update.<br/>

```json
{
  "Status": "None",
  "PreferredRegionId": "string",
  "ContactEmail": "user@example.com",
  "CommunityAlias": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The community tenant was updated.|
|204|None|No Content. No operation was performed.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it does not know how to handle.|

---

## `Patch Community Tenant Info`

<a id="opIdCommunityTenants_Patch Community Tenant Info"></a>

Updates the community tenant using an RFC 7396 compliant Patch operation.

<h3>Request</h3>

```text 
PATCH /api/v1-preview/communities/{communityId}/tenants/{tenantId}
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>Tenant identifier of the `CommunityTenant` in the community to update.<br/><br/>

<h4>Request Body</h4>

A dictionary that contains attributes found in UpdateCommunityTenantInput for a community tenant update.<br/>

```json
{
  "property1": "string",
  "property2": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The community tenant was updated.|
|204|None|No Content. No operation was performed.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it does not know how to handle.|

---

## `Remove a Community Tenant from a Community`

<a id="opIdCommunityTenants_Remove a Community Tenant from a Community"></a>

Removes a community tenant from a community

<h3>Request</h3>

```text 
DELETE /api/v1-preview/communities/{communityId}/tenants/{tenantId}
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>Tenant identifier of the `CommunityTenant` in the community to remove.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|None|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it does not know how to handle.|

---

## `Get Community Tenant Access Rights`

<a id="opIdCommunityTenants_Get Community Tenant Access Rights"></a>

Get the effective access rights for a community tenant resource.

<h3>Request</h3>

```text 
GET /api/v1-preview/communities/{communityId}/tenants/{tenantId}/accessrights
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>The requested tenant identifier.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|An enumerable of all allowed Access Rights for a CommunityTenant resource.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

---

## `Get Community Tenant Access Control List`

<a id="opIdCommunityTenants_Get Community Tenant Access Control List"></a>

Get the access control list for a community tenant resource.

<h3>Request</h3>

```text 
GET /api/v1-preview/communities/{communityId}/tenants/{tenantId}/accesscontrol
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>The requested tenant identifier.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|The AccessControlList of a CommunityTenant resource.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

---

## `Update Community Tenant Access Control List`

<a id="opIdCommunityTenants_Update Community Tenant Access Control List"></a>

Update the access control list for a community tenant resource.

<h3>Request</h3>

```text 
PUT /api/v1-preview/communities/{communityId}/tenants/{tenantId}/accesscontrol
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>The requested tenant identifier.<br/><br/>

<h4>Request Body</h4>

The new access control list to update the current entry with.<br/>

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

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

---

## `Get Community Tenant Owner`

<a id="opIdCommunityTenants_Get Community Tenant Owner"></a>

Get the resource owner for a community tenant resource.

<h3>Request</h3>

```text 
GET /api/v1-preview/communities/{communityId}/tenants/{tenantId}/owner
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>The requested tenant identifier.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|The ResourceOwner of a Community resource or empty 200 if no ResourceOwner found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

---

## `Update Community Tenant Owner`

<a id="opIdCommunityTenants_Update Community Tenant Owner"></a>

Update the resource owner for a community tenant resource.

<h3>Request</h3>

```text 
PUT /api/v1-preview/communities/{communityId}/tenants/{tenantId}/owner
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>The requested tenant identifier.<br/><br/>

<h4>Request Body</h4>

Input trustee.<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Success. Community Resource Owner is updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

---

## `List Community Tenant Extended Access Rights`

<a id="opIdCommunityTenants_List Community Tenant Extended Access Rights"></a>

Get the extended effective access rights for a community tenant resource.

<h3>Request</h3>

```text 
GET /api/v1-preview/communities/{communityId}/tenants/{tenantId}/extendedaccessrights
```

<h4>Parameters</h4>

`string communityId`
<br/>Community identifier.<br/><br/>`string tenantId`
<br/>The requested tenant identifier.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[CommunityAccessRights](#schemacommunityaccessrights)[]|An enumerable of all allowed Access Rights for an administrative CommunityTenant resource.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

<h4>Example response body</h4>

> 200 Response ([CommunityAccessRights](#schemacommunityaccessrights)[])

```json
[
  0
]
```

---
## Definitions

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Object returned whenever there is an error

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Operation identifier of action that caused the error|
|Error|string|true|false|Error description|
|Reason|string|true|false|Reason for the error|
|Resolution|string|true|false|Resolution to resolve the error|
|DynamicProperties|object|false|true|Additional properties|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "DynamicProperties": {
    "property1": null,
    "property2": null
  },
  "property1": null,
  "property2": null
}

```

---

### UpdateCommunityTenantInput

<a id="schemaupdatecommunitytenantinput"></a>
<a id="schema_UpdateCommunityTenantInput"></a>
<a id="tocSupdatecommunitytenantinput"></a>
<a id="tocsupdatecommunitytenantinput"></a>

The UpdateCommunityTenantInput object

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Status|[CommunityTenantStatus](#schemacommunitytenantstatus)|false|true|New status of CommunityTenant in community|
|PreferredRegionId|string|false|true|Change the preferred Region Id to override the community Preferred Region Id|
|ContactEmail|email|false|true|Contact email of a community tenant. It serves as a point of contact for community tenants.|
|CommunityAlias|string|false|true|Change the community alias for community tenant.|

```json
{
  "Status": "None",
  "PreferredRegionId": "string",
  "ContactEmail": "user@example.com",
  "CommunityAlias": "string"
}

```

---

### CommunityTenantStatus

<a id="schemacommunitytenantstatus"></a>
<a id="schema_CommunityTenantStatus"></a>
<a id="tocScommunitytenantstatus"></a>
<a id="tocscommunitytenantstatus"></a>

Represents a status of a community tenant.

<h4>Enumerated Values</h4>

|Property|Value|Description|
|---|---|---|
|None|None|undefined|
|Paused|Paused|undefined|
|Active|Active|undefined|

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

### CommunityAccessRights

<a id="schemacommunityaccessrights"></a>
<a id="schema_CommunityAccessRights"></a>
<a id="tocScommunityaccessrights"></a>
<a id="tocscommunityaccessrights"></a>

Access rights for operations against Communities.

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|None|0|
|ViewCommunityDetails|1|
|LeaveCommunity|2|
|ManageUsers|4|
|PauseData|8|
|EditCommunityAlias|16|
|EditCommunityProfile|32|
|DeleteCommunity|64|
|ManageTenants|128|
|ManageCommunityAdministrators|256|
|UpdateRegion|512|
|UpdateContactEmail|1024|

---

