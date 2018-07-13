# Standard Headers

## HOST \(Required\)

This determines the host that is used for the request. This value is required and should be set to one of the following:

* api.ap-southeast-2.ivvy.com
* api.us-west-2.ivvy.com
* api.eu-west-2.ivvy.com

Contact [support@ivvy.com](mailto:support@ivvy.com) if you are unsure which value to use.

`HOST: api.ap-southeast-2.ivvy.com`

## Date \(Required unless using [IVVY-Date header](custom-headers.md#ivvy-date-optional)\)

The date header determines the date the request was made. The iVvy API uses this date, compared to the date of the server to determine if the request is within the time to live setting. \(Currently requests over 5 minutes old are deemed invalid, this value may change in the future.\)

`Date: Thu, 12 Apr 2012 07:17:06 UTC`

## Content-MD5 \(Required\)

This is the md5 sum of the body of the request. This header is used to verify the contents of the body of the request have not been altered during transport. Note that if there is no content in the body, the MD5 for the request must still be calculated. See [Calculating MD5](../../../development-reference/calculating-md5.md) for more details on how to calculate the value for this field.

## Content-Type

The content type of the request body. Valid request types for the api are...

* application/json

## Content-Length

The length of the request body, in bytes.

