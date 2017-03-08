## Send Group Blocks

> Create a block allocation

```xml
<?xml version="1.0"?>
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
  <soap:Header xmlns:htnga="http://htng.org/PWSWG/2007/02/AsyncHeaders" xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wss="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
    <wss:Security mustUnderstand="1">
      <wss:UsertextToken>
        <wss:Username>test</wss:Username>
        <wss:Password>test</wss:Password>
      </wss:UsertextToken>
    </wss:Security>
    <wsa:MessageID>769479e5-4812-4475-a801-8853c54df24e</wsa:MessageID>
    <htnga:CorrelationID>769479e5-4812-4475-a801-8853c54df24e</htnga:CorrelationID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <Body>
    <OTA_HotelResNotifRQ ResStatus="Commit" TimeStamp="2016-06-08T14:55:37Z">
      <HotelReservations>
        <HotelReservation CreateDateTime="2014-06-20T22:41:51.+03:00" ResStatus="Reserved">
          <UniqueID ID="34880"/>
          <POS>
            <Source>
              <BookingChannel>
                <CompanyName Code="OTA">WEB</CompanyName>
              </BookingChannel>
            </Source>
          </POS>
          <RoomStays>
            <RoomStay MarketCode="Leisure" SourceOfBusiness="BOOKING.COM">
              <RoomRates>
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="Double">
                  <Rates>
                    <Rate EffectiveDate="2014-06-24" ExpireDate="2014-06-25" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="39.00" CurrencyCode="EUR"/>
                    </Rate>
                    <Rate EffectiveDate="2014-06-23" ExpireDate="2014-06-24" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="49.00" CurrencyCode="EUR"/>
                    </Rate>
                  </Rates>
                </RoomRate>
              </RoomRates>
              <GuestCounts>
                <GuestCount AgeQualifyingCode="10" Count="2"/>
                <GuestCount AgeQualifyingCode="8" Count="0"/>
              </GuestCounts>
              <TimeSpan End="2014-06-25" Start="2014-06-23"/>
              <BasicPropertyInfo HotelCode="44124248"/>
            </RoomStay>
          </RoomStays>
          <ResGuests>
            <ResGuest>
              <Profiles>
                <ProfileInfo>
                  <Profile>
                    <Customer>
                      <Address>
                        <CountryName Code="TC"/>
                      </Address>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>
        </HotelReservation>
        <HotelReservation CreateDateTime="2015-06-18T00:00:00.+03:00" ResStatus="Reserved">
          <UniqueID ID="42689"/>
          <POS>
            <Source>
              <BookingChannel>
                <CompanyName Code="Comp">Company</CompanyName>
              </BookingChannel>
            </Source>
          </POS>
          <RoomStays>
            <RoomStay MarketCode="Corp" SourceOfBusiness="Special Company">
              <RoomRates>
                <RoomRate NumberOfUnits="1" RatePlanCode="CORP" RoomTypeCode="SGL">
                  <Rates>
                    <Rate EffectiveDate="2015-06-25" ExpireDate="2015-06-27" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="55.00" CurrencyCode="EUR"/>
                    </Rate>
                    <Rate EffectiveDate="2015-06-22" ExpireDate="2015-06-25" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="59.00" CurrencyCode="EUR"/>
                    </Rate>
                  </Rates>
                </RoomRate>
              </RoomRates>
              <GuestCounts IsPerRoom="1">
                <GuestCount AgeQualifyingCode="10" Count="1"/>
                <GuestCount AgeQualifyingCode="8" Count="0"/>
              </GuestCounts>
              <TimeSpan End="2015-06-25" Start="2015-06-22"/>
              <BasicPropertyInfo HotelCode="44124248"/>
            </RoomStay>
          </RoomStays>
          <ResGuests>
            <ResGuest>
              <Profiles>
                <ProfileInfo>
                  <Profile>
                    <Customer>
                      <Address>
                        <CountryName Code="DEU"/>
                      </Address>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>
        </HotelReservation>
      </HotelReservations>
    </OTA_HotelResNotifRQ>
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