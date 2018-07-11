# Events

## addOrUpdateEvent

Add or update event details.

### Parameters

| Property | Type | Required | Description |
| --- | --- | --- | --- |
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
| --- | --- | --- |
| success | Whether or not the action succeeded \(i.e. the event as added or updated\). | Boolean |
| id | The event’s unique identifier. The value will be null on failure. | Integer &gt; 0 |
| code | The event’s unique code. The value will be null on failure. | String Max length: 12 |


### Example Request

`[PlatformAddress]/api/1.0/event/addOrUpdateEvent`

```javascript
{
    "eventType": 12,
  "title": "A New Event",
  "timezone": "Australia/Sydney",
  "startDateTime": "2018-03-05 03:00:00 UTC",
  "endDateTime": "2018-03-05 06:00:00 UTC",
  "capacity": 10,
  "budget": 150,
  "costCenterId": 834,
  "primaryContactUserId": 7821,
  "eventTypeIds": [56,57],
  "isAccommIncluded": false
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


| Property                  |Description                                                                   | Required | Type |
| --- | --- | --- | --- |
| perPage                   | The number of events to get in a single api call                                                                  |	| Must be an integer greater than 0 |
| start                     | The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.) |	| Must be an integer 0 or greater   |
| includeVenueDetails       | If the response should include venue details                                                                      |	| Must be a boolean                 |
| includeTicketDetails      | If the response should include ticket details                                                                     |	| Must be a boolean                 |
| includeInformationDetails | If the response should include the event information                                                              |	| Must be a boolean                 |
| includeHomepageContent    | If the response should include the homepage content of the website                                                |	| Must be a boolean                 |
| orderBy                   | Sort results                                                                                                      |	| Supported parameter “startDate”   |
| orderDir                  | Sort direction                                                                                                    |	| ‘asc’ or ‘desc’                   |


### Additional Filter Properties

| afterDate  | Filter by start date                           | [iVvy Timestamp Format](#timestamp-format) |
| beforeDate | Filter by end date                             | [iVvy Timestamp Format](#timestamp-format) |
| status     | Filter by status Array of the following values | Must be an array                           |


### Returns

Add or update event details.

| id                            | The unique event identifier                                                                                                                                                                  | 
| code                          | The code for the event                                                                                                                                                                       | 
| eventType                     | The type of event.                                                                                                                                                                           | 
| title                         | The title of the event                                                                                                                                                                       | 
| domainName                    | The domain name of the event                                                                                                                                                                 | 
| startDateTime                 | The start of the event, at UTC                                                                                                                                                               | 
| endDateTime                   | The end of the event, at UTC                                                                                                                                                                 | 
| numRegistered                 | The number of registrations                                                                                                                                                                  | 
| currentStatus                 | The current status of the event                                                                                                                                                              | 
| contactEmail                  | The contact email address on the event                                                                                                                                                       | 
| websiteUrl                    | The URL for the event website                                                                                                                                                                | 
| websiteTemplateBannerImageUrl | Banner that is displayed on the website                                                                                                                                                      | 
| venue                         | Details of the venue of the event (if the includeVenueDetails flag is set on the request)                                                                                                    | 
| name                          | The venue name                                                                                                                                                                               | 
| description                   | The description of the venue                                                                                                                                                                 | 
| address                       | The address of the venue                                                                                                                                                                     | 
| imageUrl                      | The URL to the image of the venue                                                                                                                                                            | 
| tickets                       | The tickets of an event (if the includeTicketDetails flag is set on the request)                                                                                                             | 
| id                            | The unique identifier for the ticket                                                                                                                                                         | 
| title                         | Title of the ticket                                                                                                                                                                          | 
| capacity                      | Capacity of the ticket                                                                                                                                                                       | 
| description                   | Description of the ticket                                                                                                                                                                    | 
| amount                        | Amount of the ticket                                                                                                                                                                         | 
| isTaxFree                     | Amount of the ticket is tax free                                                                                                                                                             | 
| subscriptionGroups            | Subscription groups assigned to the ticket This an array of objects with the following properties…                                                                                           | 
| id                            | The subscription group identifier                                                                                                                                                            | 
| groupName                     | The name for the group                                                                                                                                                                       | 
| tagColour                     | The designated colour for the group                                                                                                                                                          | 
| information                   | Event website information (if the includeInformationDetails flag is set on the request) This is an array of objects with the following properties…                                           | 
| description                   | Description of the information                                                                                                                                                               | 
| information                   | Content of the information                                                                                                                                                                   | 
| fileUrl                       | Attached file url of event information                                                                                                                                                       | 
| sortOrder                     | The order in which to sort the information                                                                                                                                                   | 
| homepageContent               | Content of the website home page (if the includeHomepageContent flag is set on the request). Note this is the contents of the HTML that is entered in as the home page content of the event. | 
| eventTags                     | The tags of the event                                                                                                                                                                        | 
| id                            | The unique identifier for the event tag                                                                                                                                                      | 
| name                          | The name of the event tag                                                                                                                                                                    | 
| modifiedDate                  | timestamp                                                                                                                                                                                    | 

The result from this call will be a collection of all the events the user has access to. This call also accepts the pagination and filter properties.

## getEvent

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



