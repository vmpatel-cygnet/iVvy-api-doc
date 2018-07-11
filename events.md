# Events

## addOrUpdateEvent

Add or update event details.

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- |
| id  | The event’s unique identifier. Exclude to add an event. Include to update an existing event. | Required | Integer &gt; 0 |
| eventType | The type of event. Value must be 12 \(Record Event Details\). The value cannot be changed for an existing event. | Required | Integer &gt;= 0 |
| code | The event’s unique code. Can be excluded when adding an event \(system will assign a unique code\). The value cannot be changed for an existing event. |  | String Max length: 12 |
| title | Required: when adding an event. The title of the event. |  | String Max length: 140 |
| timezone | Required: when adding an event. The timezone of the event. | Timezone |  |
| startDateTime | Required: when adding an event. The start date & time of the event. |  | Timestamp |
| endDateTime | Required: when adding an event. The end date & time of the event. The value must be on or after startDateTime. |  | Timestamp |
| capacity | The maximum number of attendees who can register for the event. A value of 0 \(zero\) represents no limit. |  | Integer &gt;= 0 |
| budget | A budget amount assigned to the event. |  | Float |
| costCenterId | A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events. |  | Integer &gt; 0 |
| primaryContactUserId | The primary contact user of the event. The value is an identifier of a user in the account. |  | Integer &gt; 0 |

This action call accepts the parameters of an event and will; 

1\) Add a new event to the account 

2\) Update an existing event in the account when the id parameter is provided.

NOTE: This action call only supports “Record Event Details” type events \(i.e. eventType value of 12\).

### Returns

| Property | Description | Type |
| --- | --- | --- | --- |
| success | Whether or not the action succeeded \(i.e. the event as added or updated\). | Boolean |
| id | The event’s unique identifier. The value will be null on failure. | Integer &gt; 0 |
| code | The event’s unique code. The value will be null on failure. | String Max length: 12 |


### Example Request

`[PlatformAddress]/api/1.0/event/addOrUpdateEvent`

```javascript
{
    "ClientToken": "E0D439EE522F44368DC78E1BFB03710C-D24FB11DBE31D4621C4817E028D9E1D",
    "AccessToken": "C66EF7B239D24632943D115EDE9CB810-EA00F8FD8294692C940F6B5A8F9453D",
    "Emails": [
        "john@doe.com"
    ]
}
```
### Example Response

```javascript
{
  "success": true,
  "id": 98481,
  "code": "BAS4G248"
}
```

## getEventList

Add or update event details.

### Parameters

### Returns

### Example Request

### Example Response

## getEventList

Add or update event details.

### Parameters

### Returns

### Example Request

### Example Response



| Property | Type |  | Description |
| --- | --- | --- | --- |
| `ClientToken` | string | required | Token identifying the client application. |
| `AccessToken` | string | required | Access token of the client application. |
| `Emails` | array of string | required | Emails of the [Customer](https://github.com/vmpatel-cygnet/iVvy-api-doc/tree/da8f3b2c149fd0c85ce9e6676e2bcac534d44bcf/events/customers.md#customer)s. |

### Response

Same structure as in [Get all customers](https://github.com/vmpatel-cygnet/iVvy-api-doc/tree/da8f3b2c149fd0c85ce9e6676e2bcac534d44bcf/events/customers.md#get-all-customers) operation.

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- |
| id  | The event’s unique identifier. Exclude to add an event. Include to update an existing event. | Required | Integer &gt; 0 |
| eventType | The type of event. Value must be 12 \(Record Event Details\). The value cannot be changed for an existing event. | Required | Integer &gt;= 0 |
| code | The event’s unique code. Can be excluded when adding an event \(system will assign a unique code\). The value cannot be changed for an existing event. |  | String Max length: 12 |
| title | Required: when adding an event. The title of the event. |  | String Max length: 140 |
| timezone | Required: when adding an event. The timezone of the event. | Timezone |  |
| startDateTime | Required: when adding an event. The start date & time of the event. |  | Timestamp |
| endDateTime | Required: when adding an event. The end date & time of the event. The value must be on or after startDateTime. |  | Timestamp |
| capacity | The maximum number of attendees who can register for the event. A value of 0 \(zero\) represents no limit. |  | Integer &gt;= 0 |
| budget | A budget amount assigned to the event. |  | Float |
| costCenterId | A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events. |  | Integer &gt; 0 |
| primaryContactUserId | The primary contact user of the event. The value is an identifier of a user in the account. |  | Integer &gt; 0 |

This action call accepts the parameters of an event and will; 

1\) Add a new event to the account 

2\) Update an existing event in the account when the id parameter is provided.

NOTE: This action call only supports “Record Event Details” type events \(i.e. eventType value of 12\).

### Response

| Property | Description | Type |
| --- | --- | --- | --- |
| success | Whether or not the action succeeded \(i.e. the event as added or updated\). | Boolean |
| id | The event’s unique identifier. The value will be null on failure. | Integer &gt; 0 |
| code | The event’s unique code. The value will be null on failure. | String Max length: 12 |

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- |
| id  | The event’s unique identifier. Exclude to add an event. Include to update an existing event. | Required | Integer &gt; 0 |
| eventType | The type of event. Value must be 12 \(Record Event Details\). The value cannot be changed for an existing event. | Required | Integer &gt;= 0 |
| code | The event’s unique code. Can be excluded when adding an event \(system will assign a unique code\). The value cannot be changed for an existing event. |  | String Max length: 12 |
| title | Required: when adding an event. The title of the event. |  | String Max length: 140 |
| timezone | Required: when adding an event. The timezone of the event. | Timezone |  |
| startDateTime | Required: when adding an event. The start date & time of the event. |  | Timestamp |
| endDateTime | Required: when adding an event. The end date & time of the event. The value must be on or after startDateTime. |  | Timestamp |
| capacity | The maximum number of attendees who can register for the event. A value of 0 \(zero\) represents no limit. |  | Integer &gt;= 0 |
| budget | A budget amount assigned to the event. |  | Float |
| costCenterId | A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events. |  | Integer &gt; 0 |
| primaryContactUserId | The primary contact user of the event. The value is an identifier of a user in the account. |  | Integer &gt; 0 |

This action call accepts the parameters of an event and will; 

1\) Add a new event to the account 

2\) Update an existing event in the account when the id parameter is provided.

NOTE: This action call only supports “Record Event Details” type events \(i.e. eventType value of 12\).

### Response

| Property | Description | Type |
| --- | --- | --- | --- |
| success | Whether or not the action succeeded \(i.e. the event as added or updated\). | Boolean |
| id | The event’s unique identifier. The value will be null on failure. | Integer &gt; 0 |
| code | The event’s unique code. The value will be null on failure. | String Max length: 12 |


```javascript
{
    "ClientToken": "E0D439EE522F44368DC78E1BFB03710C-D24FB11DBE31D4621C4817E028D9E1D",
    "AccessToken": "C66EF7B239D24632943D115EDE9CB810-EA00F8FD8294692C940F6B5A8F9453D",
    "TimeFilter": "Created",
    "StartUtc": "2016-01-01T00:00:00Z",
    "EndUtc": "2016-01-07T00:00:00Z"
}
```

| Property | Type |  | Description |
| --- | --- | --- | --- |
| `ClientToken` | string | required | Token identifying the client application. |
| `AccessToken` | string | required | Access token of the client application. |
| `TimeFilter` | string [Customer time filter](https://github.com/vmpatel-cygnet/iVvy-api-doc/tree/da8f3b2c149fd0c85ce9e6676e2bcac534d44bcf/events/customers.md#customer-time-filter) | required | Time filter of the interval. |
| `StartUtc` | string | required | Start of the interval in UTC timezone in ISO 8601 format. |
| `EndUtc` | string | required | End of the interval in UTC timezone in ISO 8601 format. |



