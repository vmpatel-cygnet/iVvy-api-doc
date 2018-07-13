# Add Discussion

## Description

Add discussion.

## Api Url

`[PlatformAddress]/api/1.0/event?action=addDiscussion`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| eventId | The unique id of the event to which the discussion belongs | Required | integer |
| sessionId | The unique id of session to which discussion belongs | Required | integer |
| attendeeId | The unique id of attendee who gives a comment | Required | integer |
| comment | The comment which will be added to discussion | Required | integer |

## Returns

| Property | Description |
| --- | --- |
| success | Whether or not the comment added to session discussion or not |
| id | The unique id of the discussion |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24186 | Must provide a from id |
| Specific Code: 24187 | The event does not exist |
| Specific Code: 24188 | The session does not exist |

## Example Request

TODO

## Example Response

TODO

