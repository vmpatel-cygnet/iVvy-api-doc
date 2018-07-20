# Get Discussion List

### Description

Get discussion list.

### API URL

`[PlatformAddress]/api/1.0/event?action=getDiscussionList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of session discussions to get in a single api call | Required | integer \(greater than 0 and maximum 100\) |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) | Required | integer \(0 or greater\) |
| from | The discussion from where to fetch belongs | Required | integer \(0 or greater\) |
| eventId | The unique id of the event to which the discussion belongs | Required | integer |
| sessionId | The unique id of session to which discussion belongs | Required | integer |

### Returns

A collection object with the following properties in the results

| Property | Description |
| --- | --- |
| id | The unique identifier of the discussion |
| name | The name on discussion |
| message | The comment on discussion |
| state | The state of the comment |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24186 | Must provide a from id |
| Specific Code: 24187 | The event does not exist |
| Specific Code: 24188 | The session does not exist |

