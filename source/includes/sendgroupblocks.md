## Send Group Blocks

```xml--create
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" 
xmlns:wsa="http://www.w3.org/2005/08/addressing" 
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
  <soap:Header>
    <wsse:Security soap:mustUnderstand="1">
      <wsse:UsernameToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
    <wsa:MessageID>8ee65699-8b8b-8427-2822-687da8b55a89</wsa:MessageID>
    <wsa:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelInvBlockNotifRQ TimeStamp="2017-05-04T14:03:10+01:00">
      <InvBlocks>
        <InvBlock InvBlockCode="FANCY_CONGRESS" TransactionAction="Book">
          <HotelRef HotelCode="45121140"/>
          <InvBlockDates AbsoluteCutoff="2017-06-01" End="2017-06-04" Start="2017-06-01"/>
          <RoomTypes>
            <RoomType End="2017-06-01" RoomTypeCode="C2T" Start="2017-06-01">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2017-06-01" NumberOfUnits="1" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="25" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="105.00" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-04" RoomTypeCode="KGB" Start="2017-06-01">
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2017-06-04" NumberOfUnits="5" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="5" RatePlanCode="GROUP2">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="90" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-03" RoomTypeCode="KGB" Start="2017-06-03">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2017-06-03" NumberOfUnits="3" Start="2017-06-03"/>
              </RoomTypeAllocations>
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2017-06-03" NumberOfUnits="1" Start="2017-06-03"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" NumberOfUnits="3" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="95" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-04" RoomTypeCode="TWB" Start="2017-06-01">
              <RoomTypeAllocations>
                <RoomTypeAllocation End="2017-06-04" NumberOfUnits="1" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" End="2017-06-02" NumberOfUnits="1" RatePlanCode="GROUP2" Start="2017-06-01">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="220" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
                <RatePlan CurrencyCode="IDR" End="2017-06-04" NumberOfUnits="1" RatePlanCode="GROUP3" Start="2017-06-02">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="110" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
          </RoomTypes>
        </InvBlock>
      </InvBlocks>
    </OTA_HotelInvBlockNotifRQ>
  </soap:Body>
</soap:Envelope>
```

```xml--modify
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" 
xmlns:wsa="http://www.w3.org/2005/08/addressing" 
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
  <soap:Header>
    <wsse:Security soap:mustUnderstand="1">
      <wsse:UsernameToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
    <wsa:MessageID>8ee65699-8b8b-8427-2822-687da8b55a89</wsa:MessageID>
    <wsa:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelInvBlockNotifRQ TimeStamp="2017-05-06T12:48:23+01:00">
      <InvBlocks>
        <InvBlock InvBlockCode="FANCY_CONGRESS" TransactionAction="Modify">
          <HotelRef HotelCode="45121140"/>
          <InvBlockDates AbsoluteCutoff="2017-06-01" End="2017-06-04" Start="2017-06-01"/>
          <RoomTypes>
            <RoomType End="2017-06-01" RoomTypeCode="C2T" Start="2017-06-01">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2017-06-01" NumberOfUnits="1" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="25" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="105.00" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-04" RoomTypeCode="KGB" Start="2017-06-01">
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2017-06-04" NumberOfUnits="5" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="5" RatePlanCode="GROUP2">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="90" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-03" RoomTypeCode="KGB" Start="2017-06-03">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2017-06-03" NumberOfUnits="3" Start="2017-06-03"/>
              </RoomTypeAllocations>
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2017-06-03" NumberOfUnits="1" Start="2017-06-03"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" NumberOfUnits="3" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="95" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-04" RoomTypeCode="TWB" Start="2017-06-01">
              <RoomTypeAllocations>
                <RoomTypeAllocation End="2017-06-04" NumberOfUnits="1" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" End="2017-06-02" NumberOfUnits="1" RatePlanCode="GROUP2" Start="2017-06-01">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="220" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
                <RatePlan CurrencyCode="IDR" End="2017-06-04" NumberOfUnits="1" RatePlanCode="GROUP3" Start="2017-06-02">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="110" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
          </RoomTypes>
        </InvBlock>
      </InvBlocks>
    </OTA_HotelInvBlockNotifRQ>
  </soap:Body>
</soap:Envelope>
```

```xml--cancel
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" 
xmlns:wsa="http://www.w3.org/2005/08/addressing" 
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
  <soap:Header>
    <wsse:Security soap:mustUnderstand="1">
      <wsse:UsernameToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
    <wsa:MessageID>8ee65699-8b8b-8427-2822-687da8b55a89</wsa:MessageID>
    <wsa:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelInvBlockNotifRQ TimeStamp="2017-05-07T16:08:13+01:00">
      <InvBlocks>
        <InvBlock InvBlockCode="FANCY_CONGRESS" TransactionAction="Cancel">
          <HotelRef HotelCode="45121140"/>
          <InvBlockDates AbsoluteCutoff="2017-05-01" End="2017-06-04" Start="2017-06-01"/>
          <RoomTypes>
            <RoomType End="2017-06-01" RoomTypeCode="C2T" Start="2017-06-01">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2017-06-01" NumberOfUnits="1" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="25" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="105.00" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-04" RoomTypeCode="KGB" Start="2017-06-01">
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2017-06-04" NumberOfUnits="5" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="5" RatePlanCode="GROUP2">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="90" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-03" RoomTypeCode="KGB" Start="2017-06-03">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2017-06-03" NumberOfUnits="3" Start="2017-06-03"/>
              </RoomTypeAllocations>
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2017-06-03" NumberOfUnits="1" Start="2017-06-03"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" NumberOfUnits="3" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="95" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2017-06-04" RoomTypeCode="TWB" Start="2017-06-01">
              <RoomTypeAllocations>
                <RoomTypeAllocation End="2017-06-04" NumberOfUnits="1" Start="2017-06-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" End="2017-06-02" NumberOfUnits="1" RatePlanCode="GROUP2" Start="2017-06-01">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="220" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
                <RatePlan CurrencyCode="IDR" End="2017-06-04" NumberOfUnits="1" RatePlanCode="GROUP3" Start="2017-06-02">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="110" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
          </RoomTypes>
        </InvBlock>
      </InvBlocks>
    </OTA_HotelInvBlockNotifRQ>
  </soap:Body>
</soap:Envelope>
```

This message permits RateManager to be alerted about a group block. We consider a group block to be a large booking (generally more than 10 rooms) that needs to be confirmed by participants and is under a specific expiration policy.

We use the HTNG 2013 specification to define the number of rooms blocked, and already sold. Each message should contain one block (one unique block id) for a single hotel.
The message processing happens like this:
1. We cross all room types, for each room type we cross all rate plans applied and save them in memory
2. We cross all counts of each block and attach them to one room type and one rate plan
3. Finally, we consider each day of the group block to create one booking with the right room type, rate plan and number of units blocked or sold

<aside class="warning">Please note that at each modification of the block, we delete the block to insert it again. That means that you must send the complete block each time.</aside>

### Fields we consider

|  |  |
| --- | --- |
| `InvBlock` | It's the block allocation block. We accept one InvBlock block for now. |
| `TransactionAction` | The transactional status of the block. It can be:<br>- 'Book' (creates a new reservation)<br>- 'Modify' (updates an existing reservation)<br>- 'Cancel' (cancels a reservation) |
| `InvBlockCode` | The unique block ID that allow us to link all future messages to the right block in our database. |
| `HotelCode` | Maps the message to a specific property. You will receive the hotel code for each new property from BookingSuite. |
| `InvBlockDates` | Global dates of the block considered. `Start` is the start date, `End` the end date, and `AbsoluteCutoff` is the release date of the block. <br>We consider the block released where AbsoluteCutoff <= Today (including today) |
| `RoomType` | One `RoomType` block is the piece of the block with a given room type and rate plan. <br>If there is only one rate plan and 2 different room types for the block, there will be at least 2 `RoomType` blocks. |
| `CompanyName` | We take this block as the source of the booking.<br>‘Code’ specifies the source (web, OTA, email, etc.), while the field is the general channel (Walk-in, WEB, TEL). |
| `RatePlan` | One `RatePlan` block gives the description of the rate plan for the given room type and time range. |
| `RatePlanCode` | The `RatePlanCode` is the rate plan code that will be shown and considered in our database, the `CurrencyCode` the currency for the given rate plan (in ISO 4217). |
| `BaseByGuestAmt` | One `BaseByGuestAmt` allow to give the amount depending of the number of people that will finally be confirmed in the booking. We save in our database only the amount for `NumberOfGuests` = 1 |
| `AmountAfterTax` | The amount after tax for the given rate plan. We don't save the amount before tax. |
| `RoomTypeAllocations` | `RoomTypeAllocations` defines the number of units per status. The statuses we consider are:<br>- 1 Definite availability<br>- 2 Tentative availability<br>- 3 Definite sold<br>- 4 Tentative sold<br><aside class="notice">The final number of units blocked for a given date will be:<br>(Definite availability + Tentative availability) - (Definite sold + Tentative sold)</aside> |
| `RoomTypeAllocation` | One `RoomTypeAllocation` line gives the number of units for the given `RoomTypePickupStatus` and a considered time range (starting with `Start`, finishing with `End`).<br>Generally, Start=End. |