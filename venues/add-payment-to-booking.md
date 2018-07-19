# Add Payment To Booking

### Description

We can add the payment details of a booking using this API. The venueId, Booking Id and payment details are required. This will also create a payment and booking invoice.

### Api Url

`[PlatformAddress]/api/1.0/venue?action=addPaymentToBooking`

### Parameters

| Property | Description | Required | Type |
| -------- | ----------- | -------- | ---- |
| venueId       | The unique id of the venue to which the booking belongs         | Required  | integer |
| bookingId     | The unique id of the booking to which the payment will be added | Required  | integer |
| payment       | The payment details to add to the booking								        |           |         |  

### Payment Details

| Property | Description | Required | Type |
| -------- | ----------- | -------- | ---- |
| paidDate      |                                             | The date & time of the payment  | Timestamp in UTC  |
| amountPaid    | The payment amount                          | Must be a valid number	        | 	                |
| paymentMethod | The payment method                          |  						                    | 	                |
| receiptNum    | A receipt number of the payment transaction | string					                | 	                |
| notes         | Additional notes about the payment          | string					                | 	                |

### Returns

| Property | Description |
| ---------| ----------- |
| success   | Whether or not the payment was added to the booking         |
| invoiceId | The unique id of the invoice to which the payment was added |
| paymentId | The unique identifier of the payment made                   |

### Throws

| Code | Description |
| ---- | ----------- |
| Specific Code: 24136 | The payment details are invalid |

### Example Request

`Add payment to booking`

```javascript
{
  "venueId": 2,
  "bookingId": 2,
  "payment": {
    "paidDate": "2015-01-22 00:00:00",
    "amountPaid": 100,
    "paymentMethod": 6,
    "receiptNum": 12345,
    "notes": "Note for payment"
  }
}
```

### Example Response

```javascript
{
  "Success": true,
  "invoiceId": 1736,
  "paymentId": 758
}
```



