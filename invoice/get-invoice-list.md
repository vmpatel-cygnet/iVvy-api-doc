# Get Invoice List

### Description

Get list of invoices.

### Api Url

`[PlatformAddress]/api/1.0/marketplace?action=getInvoiceList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of invoices to get in a single api call                                                                | Required | integer |
| start   | The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.) | Required | integer |

### Returns

A collection object with the following properties in the results

| Property | Description |
| -------- | ----------- |
| id             | The unique invoice identifier                                            |
| reference      | The unique reference number of the invoice                               |
| title          | The title of the invoice                                                 |
| description    | The description of the invoice                                           |
| currency       | The currency of the invoice                                              |
| totalCost      | The total of the invoice                                                 |
| totalTaxCost   | The tax of the invoice                                                   |
| amountPaid     | The amount paid against the invoice                                      |
| toContactEmail | The contact email of the invoice                                         |
| toContactName  | The contact name of the invoice                                          |
| currentStatus  | The status of the invoice                                                |
| createdDate    | The created date of the invoice                                          |
| modifiedDate   | The modified date of the invoice                                         |
| refType        | The reference type of the invoice                                        |
| refId          | The reference Id of the invoice                                          |
| taxRateUsed    | The tax rate percent applied to invoice                                  |
| isTaxCharged   | Whether tax charged on the invoice                                       |
| paymentDueDate | Payment due date of the invoice                                          |
| eventId        | Event Identifier to which invoice is belongs to                          |
| venueId        | Venue Identifier to which invoice is belongs to                          |
| toContactId    | Contact Id against which invoice is created                              |
| toAddress      | The “to” Address of the invoice                                          |
| bookingCode    | The unique reference code of the booking if refType is 4 (Venue Booking) |
| items          | List of invoice items Item Details                                       |
| payments       | List of payments of the invoice Payment Details                          |

### Current status

| # | Description |
| - | --- |
| 0 | Not Paid
| 1 | Un-confirmed Paid
| 2 | Paid
| 3 | Written Off
| 4 | Cancelled
| 5 | Refunded

### Reference type

| # | Description |
| - | --- |
| 0 | Custom |
| 1 | Event Registration |
| 2 | Membership Sign Up |
| 3 | Membership Renewal |
| 4 | Venue Booking |


### Address Details

| Property | Description |
| -------- | ----------- |
| line1          | Line 1 of the address (part of the "street")                             |
| line2          | Line 2 of the address (part of the "street")                             |
| line3          | Line 3 of the address (part of the "street")                             |
| line4          | Line 4 of the address (part of the "street")                             |
| city           | The city name of the address                                             |
| stateCode      | The state code of the address (e.g. QLD)                                 |
| stateName      | The state name of the address (e.g. Queensland)                          |
| countryCode    | The country code of the address (e.g. AU)                                |
| countryName    | The country name of the address (e.g. Australia)                         |
| postalCode     | The postal code of the address                                           |

### Item Details

| Property | Description |
| -------- | ----------- |
| description    | The description of the item                      |
| quantity       | Quantity of the item                             |
| unitCost       | The unit cost of the item                        |
| totalCost      | The total cost of the item                       |
| totalTaxCost   | The tax of the item                              |
| amountPaid     | The amount paid of the item'                     |
| refType        | The reference type of the item                   |


### Payment Details

| Property | Description |
| -------- | ----------- |
| paymentId      | The identifier of the payment                    |
| receiptNum     | The receipt number of the payment                |
| amountPaid     | The amount paid of the payment                   |
| notes          | The notes of the payment                         |
| chequeNumber   | The chequeNumber of the payment                  |
| paymentMethod  | The payment method of the payment                |
| paidDate       | The paid timestamp of the payment                |
| feePercentage  | The percentage fee included in amountPaid        |
| feeAmount      | The fee amount included in amountPaid            |

`Note about fee: 
If the payment is applied to multiple invoices, the fee amount is applied to the first invoice only.`

### Throws

| Code | Description |
| ---- | ----------- |
| Specific Code: 24137 | Unable to find invoice |

The invoice identifier must be provided as part of this call to fetch the specific invoice. E.g. {"id":1} can be used to fetch the details of an invoice with the identifier of 1.

