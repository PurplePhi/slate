## Receive Rate Updates

> Request body from RateManager to provider - POST url provided by you

``` xml
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:wsa="http://www.w3.org/2005/08/addressing">
  <soap:Header xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:htng="http://htng.org/PWSWG/2007/02/AsyncHeaders">
    <wsa:MessageID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:MessageID>
    <htng:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</htng:CorrelationID>
    <wsa:To>https://partners.url.com</wsa:To>
    <wsa:Action>http://htng.org/PWSWG/2010/12/RatePlan_SubmitRequest</wsa:Action>
    <wsa:ReplyTo>
      <wsa:Address>https://partners.url.com</wsa:Address>
    </wsa:ReplyTo>
    <htng:ReplyTo>
      <wsa:Address>https://api.pricematch.travel/rate_push_callback</wsa:Address>
    </htng:ReplyTo>
    <wsse:Security soap:mustUnderstand="true">
      <wsse:UsernameToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
  </soap:Header>
  <soap:Body>
    <OTA_HotelRatePlanNotifRQ TimeStamp="2016-12-05T14:57:29+00:00" Version="6.000" MessageContentCode="8">
      <RatePlans HotelCode="13864">
        <RatePlan RatePlanCode="BAR" RatePlanNotifType="Delta">
          <Rates>
            <Rate Start="2017-03-05" End="2017-03-05" CurrencyCode="EUR" InvTypeCode="DOUBLE">
              <BaseByGuestAmts>
                <BaseByGuestAmt NumberOfGuests="1" AgeQualifyingCode="10" AmountAfterTax="153" />
                <BaseByGuestAmt NumberOfGuests="2" AgeQualifyingCode="10" AmountAfterTax="173" />
              </BaseByGuestAmts>
            </Rate>
            <Rate Start="2017-03-05" End="2017-03-05" CurrencyCode="EUR" InvTypeCode="KING">
              <BaseByGuestAmts>
                <BaseByGuestAmt NumberOfGuests="1" AgeQualifyingCode="10" AmountAfterTax="163.0" />
              </BaseByGuestAmts>
            </Rate>
          </Rates>
        </RatePlan>
      </RatePlans>
    </OTA_HotelRatePlanNotifRQ>
  </soap:Body>
</soap:Envelope>
```

> GET https://api.pricematch.travel/retrieve_responses?hotel_code=hotelcode&username=user&password=pass

``` xml
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:wsa="http://www.w3.org/2005/08/addressing">
  <soap:Header xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:htng="http://htng.org/PWSWG/2007/02/AsyncHeaders">
    <wsa:MessageID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:MessageID>
    <htng:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</htng:CorrelationID>
    <wsa:To>https://partners.url.com</wsa:To>
    <wsa:Action>http://htng.org/PWSWG/2010/12/RatePlan_SubmitRequest</wsa:Action>
    <wsa:ReplyTo>
      <wsa:Address>https://partners.url.com</wsa:Address>
    </wsa:ReplyTo>
    <htng:ReplyTo>
      <wsa:Address>https://api.pricematch.travel/rate_push_callback</wsa:Address>
    </htng:ReplyTo>
    <wsse:Security soap:mustUnderstand="true">
      <wsse:UsernameToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
  </soap:Header>
  <soap:Body>
    <OTA_HotelRatePlanNotifRQ TimeStamp="2016-12-05T14:57:29+00:00" Version="6.000" MessageContentCode="8">
      <RatePlans HotelCode="13864">
        <RatePlan RatePlanCode="BAR" RatePlanNotifType="Delta">
          <Rates>
            <Rate Start="2017-03-05" End="2017-03-05" CurrencyCode="EUR" InvTypeCode="DOUBLE">
              <BaseByGuestAmts>
                <BaseByGuestAmt NumberOfGuests="1" AgeQualifyingCode="10" AmountAfterTax="153" />
                <BaseByGuestAmt NumberOfGuests="2" AgeQualifyingCode="10" AmountAfterTax="173" />
              </BaseByGuestAmts>
            </Rate>
            <Rate Start="2017-03-05" End="2017-03-05" CurrencyCode="EUR" InvTypeCode="KING">
              <BaseByGuestAmts>
                <BaseByGuestAmt NumberOfGuests="1" AgeQualifyingCode="10" AmountAfterTax="163.0" />
              </BaseByGuestAmts>
            </Rate>
          </Rates>
        </RatePlan>
      </RatePlans>
    </OTA_HotelRatePlanNotifRQ>
  </soap:Body>
</soap:Envelope>
```

This message allows us to notify your system about rate updates that a property would like to perform, and lets you handle channel management. These rate updates can be triggered manually by the property, or automatically according to RateManager settings decided by the property (difference with the current price, dates, etc...).

The message contains the list of the new prices for different check-in dates and their corresponding conditions (room type, the number of guests, and the rate plan). Since our Revenue Management System and your system use different codes (hotel codes, room codes, etc.), we should agree beforehand on which system codes we should use in the message. By default, we assume we will use all your system codes. Please let us know if you want to do otherwise.
<aside class="notice">All rates we push have been approved by the user first - any updates that are implemented have been analyzed and validated by the property owner.</aside>

### Push Mode (POST from RateManager to your system)

You must provide a web service to which we can send HTTP POST requests with the `OTA_HotelRatePlanNotifRQ` message inside a SOAP envelope as the body. You have to apply the updates asynchronously: this means you have to respond to our POST before trying to send the rate updates to any other system. The response should be quick, regardless of the number of rate updates, and any costly computation that takes more than few seconds should be performed asynchronously.

You must also inform us about the success or the failure of the rate push by sending a POST request to the callback url. If the update failed, you must provide us with a helpful error message to understand the issue. It will help us fix a whole range of problems without involving your support team, and make communication easy and efficient. You should provide different error messages for the following errors:

* If the username/password is wrong
* If the connection is not activated/configured
* If the hotel code is not correct or not associated with the username/password.
* If the rate plan is wrong
* If one of the room codes is wrong (please specify which code(s))
* If anything else prevented the success of the rate update

<aside class="notice">Regarding security, we use dynamic IP, so please do not use any IP whitelisting for your web service. If you are concerned with security, please enable SSL/HTTPS.</aside>

### Pull Mode (GET from your system to RateManager)

You can also choose to collect the rate updates from our system via a GET. In this mode, you should hit our endpoint periodically, ideally every 5 minutes or so, to receive the rate updates that haven't been sent yet.

`GET https://api.pricematch.travel/retrieve_responses?hotel_code=hotelcode&username=user&password=pass`

This endpoint works as a queueing system. Meaning that when you send a GET request, If we have rate updates to send, you will get only the one on top of the queue, and we’ll delete it from our system. So that when you GET again, the next rate update will be send.

If we don't have any rate updates to send, we'll respond with a 204 status code (no content).

When receiving a rate, you should keep sending another GET request in a loop, until you receive a 204. That’s very important, otherwise you might get into a condition where you never manage to fetch all the rates updates we have.

### Fields we consider

|  |  |
| --- | --- |
| `<wsa:MessageID>9ff77969-348d</wsa:MessageID>` | The `MessageID`. You should use it inside the asynchronous callback message. |
| `<wsa:Address>https://api.pricematch.travel/rate_plan_notif_callback</wsa:Address>` | The URL to send the asynchronous call back message. |
| `<wsse:UsernameToken>` | This field will contain your web service credentials. It can be one username/password for all properties, or a different username/password for each property.<aside class="notice">The first possibility (one username/password for all properties) is easier to manage.</aside> |
| `<RatePlans HotelCode="13864">` | The `Hotel Code` variable maps the message to a specific property. This code must be defined by you. |
| `<RatePlan RatePlanCode="BAR">`| The rate policy code we refer to. If your system doesn’t support different rate policies, we can send a default value like BAR. |
| `<Rate Start="2017-03-05" End="2017-03-05">` | `Start` and `End` are the date range attributes. Both are inclusive. |
| `<Rate CurrencyCode="EUR">` | `Currency` is the currency considered for this rate block. |
| `<Rate InvTypeCode="DOUBLE">` | `InvTypeCode` can be anything that enable us to uniquely identify a room type for a given hotel. It could be a room type or a room code (your choice). |
| <BaseByGuestAmt NumberOfGuests="1" AmountAfterTax="155"> | `NumberOfGuest` is the number of guests considered for the given amount, rate policy and room type.<br>`AmountAfterTax` is a positive numeric value that is the rate to apply for the given rate policy, room type and number of people. |