# Get Event List


## Description

Get list of event.

## API Url

`[PlatformAddress]/api/1.0/event?action=getEventList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of events to get in a single api call. | Required | integer |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) |  | Must be an integer 0 or greater |
| includeVenueDetails | If the response should include venue details |  | Must be a boolean |
| includeTicketDetails | If the response should include ticket details |  | Must be a boolean |
| includeInformationDetails | If the response should include the event information |  | Must be a boolean |
| includeHomepageContent | If the response should include the homepage content of the website |  | Must be a boolean |
| orderBy | Sort results |  | Supported parameter “startDate” |
| orderDir | Sort direction |  | ‘asc’ or ‘desc’ |

### Additional Filter Properties

| Property | Description | Type |
| --- | --- | --- |
| afterDate | Filter by start date | [iVvy Timestamp Format](./#timestamp-format) |
| beforeDate | Filter by end date | [iVvy Timestamp Format](./#timestamp-format) |
| status | Filter by status Array of the following values | Must be an array |

### Returns

Add or update event details.

| Property | Description |
| --- | --- |
| id | The unique event identifier |
| code | The code for the event |
| eventType | The type of event. |
| title | The title of the event |
| domainName | The domain name of the event |
| startDateTime | The start of the event, at UTC |
| endDateTime | The end of the event, at UTC |
| numRegistered | The number of registrations |
| currentStatus | The current status of the event |
| contactEmail | The contact email address on the event |
| websiteUrl | The URL for the event website |
| websiteTemplateBannerImageUrl | Banner that is displayed on the website |
| venue | Details of the venue of the event \(if the includeVenueDetails flag is set on the request\) |
| name | The venue name |
| description | The description of the venue |
| address | The address of the venue |
| imageUrl | The URL to the image of the venue |
| tickets | The tickets of an event \(if the includeTicketDetails flag is set on the request\) |
| id | The unique identifier for the ticket |
| title | Title of the ticket |
| capacity | Capacity of the ticket |
| description | Description of the ticket |
| amount | Amount of the ticket |
| isTaxFree | Amount of the ticket is tax free |
| subscriptionGroups | Subscription groups assigned to the ticket This an array of objects with the following properties… |
| id | The subscription group identifier |
| groupName | The name for the group |
| tagColour | The designated colour for the group |
| information | Event website information \(if the includeInformationDetails flag is set on the request\) This is an array of objects with the following properties… |
| description | Description of the information |
| information | Content of the information |
| fileUrl | Attached file url of event information |
| sortOrder | The order in which to sort the information |
| homepageContent | Content of the website home page \(if the includeHomepageContent flag is set on the request\). Note this is the contents of the HTML that is entered in as the home page content of the event. |
| eventTags | The tags of the event |
| id | The unique identifier for the event tag |
| name | The name of the event tag |
| modifiedDate | timestamp |

The result from this call will be a collection of all the events the user has access to. This call also accepts the pagination and filter properties.
