# Add Response

## Description

Add poll response.

## Api Url

`[PlatformAddress]/api/1.0/event?action=addResponse`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| eventId | The unique id of the event to which the poll belongs | Required | integer |
| pollId | The unique id of the poll to which reponse belongs | Required | integer |
| sessionId | The unique id of the session to which reponse belongs | Required | integer |
| attendeeId | The unique id of attendee who gives an response | Required | integer |
| answerId | The unique id of poll answer | Required | integer |

## Returns

| Property | Description |
| --- | --- |
| success | Whether or not the response added to poll or not |
| id | The unique id of the response |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24175 | The request is empty |
| Specific Code: 24175 | The event does not exist |
| Specific Code: 24176 | The poll does not exist |
| Specific Code: 24177 | The event poll response details are invalid |

## Example Request

TODO

## Example Response

TODO

