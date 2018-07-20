# Get Poll

### Description

Get poll details.

### API URL

`[PlatformAddress]/api/1.0/event?action=getPoll`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The event poll identifier | Required | integer |
| eventId | The unique id of the event to which the poll belongs | Required | integer |

### Returns

| Property | Description |
| --- | --- |
| id | The unique identifier of the poll |
| question | The name of the question |
| sessions | An array of objects with the sesssion properties |
| answers | An array of objects with the answer properties |

### Session properties

| Property | Description |
| --- | --- |
| id | The unique identifier of the session |
| name | The name of the session |

### Answers properties

| Property | Description |
| --- | --- |
| id | The unique id of answer |
| answer | The answer of the question |

The details of the poll will also include a list of sessions that this poll is attached to. It is possiblethat this list may be empty, which would indicate the poll is not specific to any session, but theevent of a whole

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24173 | The event does not exist |
| Specific Code: 24214 | Valid id must be require to find poll detail |
| Specific Code: 24174 | Unable to find event poll |

