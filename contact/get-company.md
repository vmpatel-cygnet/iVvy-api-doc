# Get Company

### Description

Get comapny detail.

### Api Url

`[PlatformAddress]/api/1.0/contact?action=getCompanyList`

### Parameters

| Description | Required | Type |
| --- | --- | --- |
| The company’s identifier | Required | integer |

### Returns

| Property | Description |
|----------------|------------------------------------------------------------------------------------------|
| id             | The unique identifier for the company                                                    |
| externalId     | Optionally a unique identifier of the company that is managed by an external application |
| businessName   | The company's business name                                                              |
| tradingName    | The company's trading name                                                               |
| businessNumber | The company's registration number                                                        |
| phone          | The company's phone number                                                               |
| fax            | The company's fax number                                                                 |
| website        | The company's website                                                                    |
| email          | The company's email address                                                              |
| address        | The company’s address. This is an an object with the [keys](get-company.md#keys)         |
| modifiedDate   | The modified date of the company                                                         |

### Keys

| keys |
|------|
| line1 |  
| line2 | 
| line3 | 
| line4 | 
| city | 
| stateCode (e.g: QLD) | 
| countryCode (e.g: AU) | 
| postalCode | 

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

