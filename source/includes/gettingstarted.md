## Getting Started

### Overview

> API endpoint

```
https://api.pricematch.travel/htng_message
```

Our specification is based on the [HTNG 2013B](https://s3-eu-west-1.amazonaws.com/static-assets-20120401/HTNG/Technical+specification+documents.zip) specification, as created by the <a href="http://www.htng.org/" target="_blank">Hotel Technology Next Generation Association</a>. All relevant code and details that we use will be explained in the following sections for your convenience. Refer to the HTNG 2013B specification at your own discretion and necessity.

The XML messages that will be sent and received are to be written in <a href="https://www.tutorialspoint.com/soap/soap_message_structure.htm" target="_blank">SOAP Message structure</a>. We support both SOAP 1.1 and 1.2 versions. Specifically, these messages are:

From PMS to BookingSuite RateManager (1-Way Connection):

* **OTA_HotelInvCountNotifRQ** message to post inventory data (number of rooms built, sold available...)
* **OTA_HotelResNotifRQ** message to post reservation creation, modification, cancellation
* **OTA_HotelInvBlockNotifRQ** message to post group block allocation creation, modification, cancellation

From BookingSuite RateManager to the PMS or Channel manager (2-Way Connection)

* **OTA_RatePlanNotifRQ** message: BookingSuite RateManager posts rates triggered by user's validation on our website.

###Authentication

> Authentication

```xml
<Header>
  <Security mustUnderstand="true">
    <UsertextToken>
      <Username>username_goes_here</Username>
      <Password>password_goes_here</Password>
    </UsertextToken>
  </Security>
</Header>
```

We authenticate inbound messages with the SOAP protocol’s `<Security>` field. We will provide you with a username and password to put into the header.

Without this block, you will get a 400 error with the error message: "SOAP Header not valid". 

You should receive credentials when beginning the development phase - if not, please contact bookingsuite.connectivity@booking.com.

### Message type summary

HTNG type | Goal | Mandatory? | Direction
--------- | ---- | ---------- | ---------
OTA_HotelResNotifRQ | Receiving property reservation data | Yes | PMS -> RateManager
OTA_HotelInvCountNotifRQ | Receiving property inventory data | Yes | PMS -> RateManager
OTA_HotelInvBlockNotifRQ | Receiving property group block data | No | PMS -> RateManager
OTA_RatePlanNotifRQ | Receiving rate update validated by the customer | Yes | RateManager -> PMS