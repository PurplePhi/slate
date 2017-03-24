## Send Group Blocks

```xml--create
<?xml version="1.0"?>
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
  <soap:Header>
    <wsse:Security soap:mustUnderstand="1">
      <wsse:UsernameToken>
        <wsse:Username>UserName</wsse:Username>
        <wsse:Password>Pass</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
    <wsa:MessageID>8ee65699-8b8b-8427-2822-687da8b55a89</wsa:MessageID>
    <wsa:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <Body>
    <OTA_HotelInvBlockNotifRQ TimeStamp="2015-05-04T15:35:31.953125+07:00">
      <InvBlocks>
        <InvBlock InvBlockCode="XMAS13" TransactionAction="Book">
          <HotelRef HotelCode="HXCAIZZ"/>
          <InvBlockDates AbsoluteCutoff="2015-06-01" End="2015-03-04" Start="2015-03-01"/>
          <RoomTypes>
            <RoomType End="2015-03-01" RoomTypeCode="C2T" Start="2015-03-01">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2015-03-01" NumberOfUnits="1" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="25" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="105.00"00" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-04" RoomTypeCode="KGB" Start="2015-03-01">
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2015-03-04" NumberOfUnits="5" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="5" RatePlanCode="GROUP2">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="90"" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-03" RoomTypeCode="KGB" Start="2015-03-03">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2015-03-03" NumberOfUnits="3" Start="2015-03-03"/>
              </RoomTypeAllocations>
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2015-03-03" NumberOfUnits="1" Start="2015-03-03"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" NumberOfUnits="3" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="95"" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-04" RoomTypeCode="TWB" Start="2015-03-01">
              <RoomTypeAllocations>
                <RoomTypeAllocation End="2015-03-04" NumberOfUnits="1" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" End="2015-03-02" NumberOfUnits="1" RatePlanCode="GROUP2" Start="2015-03-01">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="220" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
                <RatePlan CurrencyCode="IDR" End="2015-03-04" NumberOfUnits="1" RatePlanCode="GROUP3" Start="2015-03-02">
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
  </Body>
</Envelope>
```

```xml--modify
<?xml version="1.0"?>
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
  <soap:Header>
    <wsse:Security soap:mustUnderstand="1">
      <wsse:UsernameToken>
        <wsse:Username>UserName</wsse:Username>
        <wsse:Password>Pass</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
    <wsa:MessageID>8ee65699-8b8b-8427-2822-687da8b55a89</wsa:MessageID>
    <wsa:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <Body>
    <OTA_HotelInvBlockNotifRQ TimeStamp="2015-05-04T15:35:31.953125+07:00">
      <InvBlocks>
        <InvBlock InvBlockCode="XMAS13" TransactionAction="Modify">
          <HotelRef HotelCode="HXCAIZZ"/>
          <InvBlockDates AbsoluteCutoff="2015-02-01" End="2015-03-04" Start="2015-03-01"/>
          <RoomTypes>
            <RoomType End="2015-03-01" RoomTypeCode="C2T" Start="2015-03-01">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2015-03-01" NumberOfUnits="1" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="25" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="105.00"00" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-04" RoomTypeCode="KGB" Start="2015-03-01">
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2015-03-04" NumberOfUnits="5" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="5" RatePlanCode="GROUP2">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="90"" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-03" RoomTypeCode="KGB" Start="2015-03-03">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2015-03-03" NumberOfUnits="3" Start="2015-03-03"/>
              </RoomTypeAllocations>
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2015-03-03" NumberOfUnits="1" Start="2015-03-03"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" NumberOfUnits="3" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="95"" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-04" RoomTypeCode="TWB" Start="2015-03-01">
              <RoomTypeAllocations>
                <RoomTypeAllocation End="2015-03-04" NumberOfUnits="1" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" End="2015-03-02" NumberOfUnits="1" RatePlanCode="GROUP2" Start="2015-03-01">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="220" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
                <RatePlan CurrencyCode="IDR" End="2015-03-04" NumberOfUnits="1" RatePlanCode="GROUP3" Start="2015-03-02">
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
  </Body>
</Envelope>
```

```xml--cancel
<?xml version="1.0"?>
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
  <soap:Header>
    <wsse:Security soap:mustUnderstand="1">
      <wsse:UsernameToken>
        <wsse:Username>UserName</wsse:Username>
        <wsse:Password>Pass</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
    <wsa:MessageID>8ee65699-8b8b-8427-2822-687da8b55a89</wsa:MessageID>
    <wsa:CorrelationID>9ff77969-348d-4ed5-bc64-e7a5df4f0f9b</wsa:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <Body>
    <OTA_HotelInvBlockNotifRQ TimeStamp="2015-05-04T15:35:31.953125+07:00">
      <InvBlocks>
        <InvBlock InvBlockCode="XMAS13" TransactionAction="Cancel">
          <HotelRef HotelCode="HXCAIZZ"/>
          <InvBlockDates AbsoluteCutoff="2015-02-01" End="2015-03-04" Start="2015-03-01"/>
          <RoomTypes>
            <RoomType End="2015-03-01" RoomTypeCode="C2T" Start="2015-03-01">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2015-03-01" NumberOfUnits="1" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="25" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="105.00"00" NumberOfGuests="1"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-04" RoomTypeCode="KGB" Start="2015-03-01">
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2015-03-04" NumberOfUnits="5" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="EUR" NumberOfUnits="5" RatePlanCode="GROUP2">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="90"" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-03" RoomTypeCode="KGB" Start="2015-03-03">
              <RoomTypeAllocations RoomTypePickUpStatus="2">
                <RoomTypeAllocation End="2015-03-03" NumberOfUnits="3" Start="2015-03-03"/>
              </RoomTypeAllocations>
              <RoomTypeAllocations RoomTypePickUpStatus="4">
                <RoomTypeAllocation End="2015-03-03" NumberOfUnits="1" Start="2015-03-03"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" NumberOfUnits="3" RatePlanCode="GROUP1">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="95"" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
              </RatePlans>
            </RoomType>
            <RoomType End="2015-03-04" RoomTypeCode="TWB" Start="2015-03-01">
              <RoomTypeAllocations>
                <RoomTypeAllocation End="2015-03-04" NumberOfUnits="1" Start="2015-03-01"/>
              </RoomTypeAllocations>
              <RatePlans>
                <RatePlan CurrencyCode="IDR" End="2015-03-02" NumberOfUnits="1" RatePlanCode="GROUP2" Start="2015-03-01">
                  <BaseByGuestAmts>
                    <BaseByGuestAmt AmountAfterTax="220" NumberOfGuests="2"/>
                  </BaseByGuestAmts>
                </RatePlan>
                <RatePlan CurrencyCode="IDR" End="2015-03-04" NumberOfUnits="1" RatePlanCode="GROUP3" Start="2015-03-02">
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
  </Body>
</Envelope>
```

This message permits RateManager to be alerted about a group block. We consider a group block to be a large booking (generally more than 10 rooms) that needs to be confirmed by participants and is under a specific expiration policy.

We use the HTNG 2013 specification to define the number of rooms blocked, and already sold. Each message should contain one block (one unique block id) for a single hotel.
The message processing happens like this:
1. We cross all room types, for each room type we cross all rate plans applied and save them in memory
2. We cross all counts of each block and attach them to one room type and one rate plan
3. Finally, we consider each day of the group block to create one booking with the right room type, rate plan and number of units blocked or sold

<aside class="warning">Please note that at each modification of the block, we delete the block to insert it again. That means that you must send the complete block each time.</aside>