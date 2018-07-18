# Add Contacts To Subscription Group

### Description

Add or update event details.

### Api Url

`[PlatformAddress]/api/1.0/batch?action=run`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| contacts | The contact identifiers to subscribe to the group        | Required | This is an array of contact identifiers (each must be a valid integer) |
| group    | The subscription group identifier to add the contacts to | Required | Must be a valid integer.                                               |
### Returns

An array of objects with the following properties

| Property | Description |
|-----------|----------------------------------------------|
| contactId | The contact this result is for               |
| status    | If the contact was added to the group or not |

### `Adds a number of contacts to a subscription group.`

### Example Request

 Add 4 contacts to subscription group 2481
 
```javascript
{
  "contacts": [
    4,
    6,
    55,
    33
  ],
  "group": 2481
}
```

### Example Response

```javascript
[
  {
    "contactId": 4,
    "status": true
  },
  {
    "contactId": 6,
    "status": true
  },
  {
    "contactId": 55,
    "status": true
  },
  {
    "contactId": 33,
    "status": false
  }
]
```
