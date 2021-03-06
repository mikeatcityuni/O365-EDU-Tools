# Update educationuser

Update the properties of educationuser object.
## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](../../../concepts/permissions_reference.md).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) |  Not supported.  |
|Delegated (personal Microsoft account) |  Not supported.  |
|Application | EduRoster.ReadWrite.All |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /education/me
PATCH /education/users/<id>
```
## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |
| Content-Type  | application/json  |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|displayName| String| Display Name of User|
|givenName| String | First Name |
|middleName| String | Middle Name of user|
|surname| String | Surname of user|
|mail| String| email address|
|mobilePhone| String | Mobile number of user |
|externalSource|string| Possible values are: `sis`, `manual`, `enum_sentinel`.|
|externalSource|string| Where this user was created from.  Possible values are: `sis`, `manual`, `enum_sentinel`.|
|mailingAddress|[physicalAddress](physicaladdress.md)| Mail address of user.|
|residenceAddress|[physicalAddress](physicaladdress.md)| Address where user lives.|
|primaryRole|string| Default Role for a user.  The user's role might be different in an individual class. Possible values are: `student`, `teacher`, `enum_sentinel`.|
|student|[educationStudent](../resources/educationstudent.md)| If the primary role is student, this block will contain student specific data.|
|teacher|[educationTeacher](../resources/educationteacher.md)| If the primary role is teacher, this block will conatin teacher specific data.|


## Response
If successful, this method returns a `200 OK` response code and updated [educationUser](../resources/educationuser.md) object in the response body.
## Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_educationuser"
}-->
```http
PATCH https://graph.microsoft.com/beta/education/users/<id>
Content-type: application/json
Content-length: 508

{
  "displayName": "string",
  "givenName": "string",
  "middleName": "string",
  "surname": "string",
}
```
##### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationUser"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 508

{
  "id": "string",
  "displayName": "string",
  "givenName": "string",
  "middleName": "string",
  "surname": "string",
  "mail": "string",
  "mobilePhone": "string",
  "createdBy": {"@odata.type": "microsoft.graph.identitySet"},
  "externalSource": "string",
  "mailingAddress": {"@odata.type": "microsoft.graph.physicalAddress"},
  "primaryRole": "string",
  "residenceAddress": {"@odata.type": "microsoft.graph.physicalAddress"},
  "student": {"@odata.type": "microsoft.graph.educationStudent"},
  "teacher": {"@odata.type": "microsoft.graph.educationTeacher"}
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update educationuser",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->