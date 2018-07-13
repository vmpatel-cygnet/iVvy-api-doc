# Add Question

## Description

Add question.

## Api Url

`[PlatformAddress]/api/1.0/event?action=addQuestion`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| eventId | The unique id of the event to which the poll belongs | Required | integer |
| sessionId | The unique id of session to which question belongs | Required | integer |
| attendeeId | The unique id of attendee who adds a question | Required | integer |
| question | The question which will be added to session | Required | integer |

## Returns

| Property | Description |
| --- | --- |
| success | Whether or not the question added to session or not |
| id | The unique id of the question |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24197 | The request is empty |
| Specific Code: 24198 | The event does not exist |
| Specific Code: 24199 | The session does not exist |
| Specific Code: 24200 | The session question details are invalid |

## Example Request

TODO

## Example Response

TODO

