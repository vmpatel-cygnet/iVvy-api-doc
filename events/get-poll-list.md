# Get Poll List

### Description

Get poll list.

### Api Url

`[PlatformAddress]/api/1.0/event?action=getPollList`

### Parameters


| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of event polls to get in a single api call                                                             | Required | integer (greater than 0 and maximum 100) |
| start   | The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.) | Required | integer (0 or greater) |
| eventId | The unique id of the event to which the poll belongs                                                              | Required | integer |

### Returns

A collection object with the following properties in the results

| Property | Description |
|----------|---------------------------------------------------|
| id       | The unique identifier of the poll                 |
| question | The name of the question                          |
| sessions | An array of objects with the session properties   |

### Session properties

| Property | Description |
|----------|---------------------------------------------------|
| id       | The unique identifier of the session              |
| name     | The name of the session                           |

The result from this call will be a collection of all the event polls the user
has access to. This call also accepts the pagination and filter properties.

### Throws

| Code | Description |
|----------------------|--------------------------|
| Specific Code: 24172 | The event does not exist |

### Example Request

TODO 

### Example Response

TODO

