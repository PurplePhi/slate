## Send Reservations

```xml--create
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema" 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:wsa="http://www.w3.org/2005/08/addressing">
  <soap:Header>
    <wsse:Security xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" 
      soap:mustUnderstand="1">
      <wsse:UsertextToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsertextToken>
    </wsse:Security>
    <wsa:MessageID>unique_message_ID</wsa:MessageID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelResNotifRQ ResStatus="Commit" TimeStamp="2017-04-04T10:01:29+01:00">
      <HotelReservations>
        <HotelReservation CreateDateTime="2017-04-04T10:00:15+01:00" ResStatus="Reserved">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="King" InvBlockCode="">
                  <Rates>
                    <Rate EffectiveDate="2017-05-01" ExpireDate="2017-05-02" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="39.00" CurrencyCode="EUR"/>
                    </Rate>
                    <Rate EffectiveDate="2017-05-02" ExpireDate="2017-05-03" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="49.00" CurrencyCode="EUR"/>
                    </Rate>
                  </Rates>
                </RoomRate>
              </RoomRates>
              <GuestCounts>
                <GuestCount AgeQualifyingCode="10" Count="2"/>
                <GuestCount AgeQualifyingCode="8" Count="0"/>
              </GuestCounts>
              <BasicPropertyInfo HotelCode="45121140"/>
            </RoomStay>
          </RoomStays>
          <ResGuests>
            <ResGuest>
              <Profiles>
                <ProfileInfo>
                  <Profile>
                    <Customer>
                      <Address>
                        <CountryName Code="UK"/>
                      </Address>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>
        </HotelReservation>
        <HotelReservation CreateDateTime="2017-04-15T10:00:13+01:00" ResStatus="Reserved">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="CORP" RoomTypeCode="Deluxe" InvBlockCode="">
                  <Rates>
                    <Rate EffectiveDate="2017-05-01" ExpireDate="2017-05-02" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="55.00" CurrencyCode="EUR"/>
                    </Rate>
                    <Rate EffectiveDate="2017-05-02" ExpireDate="2017-05-03" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="59.00" CurrencyCode="EUR"/>
                    </Rate>
                  </Rates>
                </RoomRate>
              </RoomRates>
              <GuestCounts IsPerRoom="1">
                <GuestCount AgeQualifyingCode="10" Count="2"/>
                <GuestCount AgeQualifyingCode="8" Count="0"/>
              </GuestCounts>
              <BasicPropertyInfo HotelCode="45121140"/>
            </RoomStay>
          </RoomStays>
          <ResGuests>
            <ResGuest>
              <Profiles>
                <ProfileInfo>
                  <Profile>
                    <Customer>
                      <Address>
                        <CountryName Code="DE"/>
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
  </soap:Body>
</soap:Envelope>
```

```xml--modify
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema" 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:wsa="http://www.w3.org/2005/08/addressing">
  <soap:Header>
    <wsse:Security xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" 
      soap:mustUnderstand="1">
      <wsse:UsertextToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsertextToken>
    </wsse:Security>
    <wsa:MessageID>unique_message_ID</wsa:MessageID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelResNotifRQ ResStatus="Modify" TimeStamp="2017-04-05T12:09:33+01:00">
      <HotelReservations>
        <HotelReservation CreateDateTime="2017-04-04T10:00:15+01:00" ResStatus="Reserved">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="King" InvBlockCode="">
                  <Rates>
                    <Rate EffectiveDate="2017-05-01" ExpireDate="2017-05-02" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="39.00" CurrencyCode="EUR"/>
                    </Rate>
                  </Rates>
                </RoomRate>
              </RoomRates>
              <GuestCounts>
                <GuestCount AgeQualifyingCode="10" Count="2"/>
                <GuestCount AgeQualifyingCode="8" Count="0"/>
              </GuestCounts>
              <BasicPropertyInfo HotelCode="45121140"/>
            </RoomStay>
          </RoomStays>
          <ResGuests>
            <ResGuest>
              <Profiles>
                <ProfileInfo>
                  <Profile>
                    <Customer>
                      <Address>
                        <CountryName Code="UK"/>
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
  </soap:Body>
</soap:Envelope>
```

```xml--cancel
<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema" 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:wsa="http://www.w3.org/2005/08/addressing">
  <soap:Header>
    <wsse:Security xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" 
      soap:mustUnderstand="1">
      <wsse:UsertextToken>
        <wsse:Username>username</wsse:Username>
        <wsse:Password>password</wsse:Password>
      </wsse:UsertextToken>
    </wsse:Security>
    <wsa:MessageID>unique_message_ID</wsa:MessageID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelResNotifRQ ResStatus="Cancel" TimeStamp="2017-04-06T09:23:48+01:00">
      <HotelReservations>
        <HotelReservation CreateDateTime="2017-04-04T10:00:15+01:00" ResStatus="Cancelled">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="King" InvBlockCode="">
                  <Rates>
                    <Rate EffectiveDate="2017-05-01" ExpireDate="2017-05-02" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="39.00" CurrencyCode="EUR"/>
                    </Rate>
                  </Rates>
                </RoomRate>
              </RoomRates>
              <GuestCounts>
                <GuestCount AgeQualifyingCode="10" Count="2"/>
                <GuestCount AgeQualifyingCode="8" Count="0"/>
              </GuestCounts>
              <BasicPropertyInfo HotelCode="45121140"/>
            </RoomStay>
          </RoomStays>
          <ResGuests>
            <ResGuest>
              <Profiles>
                <ProfileInfo>
                  <Profile>
                    <Customer>
                      <Address>
                        <CountryName Code="UK"/>
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
  </soap:Body>
</soap:Envelope>
```

This endpoint posts a new reservation creation, modification or cancellation to BookingSuite RateManager. The immediate response is a standard HTTP code (Ack / Nack).

Each OTA_HotelResNotifRQ message can contain up to 1000 reservations for a single hotel. These reservations are in a `<HotelReservation>` block, and must be gathered under the same transactional status.

| Fields we consider |  |
| --- | --- |
| `OTA_ResNotifRQ`<br>`ResStatus` | Transactional status of the reservation. It can be:<br>- 'Commit' (creates a new reservation)<br>- 'Modify' (updates an existing reservation)<br>- 'Cancel' (cancels a reservation) |
| `<HotelReservation>` | Reservation block. We accept up to 1000 blocks. |
| `CreateDateTime` | This is what we consider as the booking date. Please ensure the timezone matches that of the property. Format 2016-10-09T08:51:45 UTC |
| `HotelReservation`<br>`ResStatus` | Reservation status. It can be:<br>- Reserved (confirmed reservation)<br>- Waitlisted(reservation on waitlist)<br>- In-House (in-house booking)<br>- Checked-Out (already checked-out reservation)<br>- Cancelled (already cancelled reservation)<br> <aside class="warning">Not to be confused with `OTA_ResNotifRQ ResStatus`</aside>|
| `UniqueID` | Unique reservation ID of the reservation that will permit us to link your message to the reservation in our database. |
| `HotelCode` | Maps the message to a specific property. You will receive the hotel code for each new property from BookingSuite. |
| `CompanyName` | We take this block as the source of the booking.<br>‘Code’ specifies the source (web, OTA, email, etc.), while the field is the general channel (Walk-in, WEB, TEL). |
| `RoomStay` | One `<Roomstay>` block is one room booked for the given reservation. |
| `MarketCode` | `MarketCode` is the intent of the stay, and what we take as segmentation data (leisure, corporate, etc). |
| `SourceOfBusiness` | `SourceOfBusiness` is what we take as the agency. |
| `RoomRate` | One `<RoomRate>` block represents one rate for one rate plan and one room type.<aside class="notice">If the booking has 2 different room types, there will be at least 2 `RoomRate` blocks. If a booking has one room type, with 2 nights with a different rate plan, there will be 2 `RoomRate` blocks.</aside> |
| `RoomTypeCode` | Room type. It must match the `InvTypeCode` in inventory messages. |
| `RatePlanCode` | Rate plan used for this reservation |
| `NumberOfUnits` | Number of rooms under the same roomtype and rate plan. |
| `InvBlockCode` | If the room booked is part of a block, the block ID is transferred in this field. |
| `Rate` | One `<Rate>` block is for one amount for the given rate plan and room type for a given period.<aside class="notice">If the rate plan implies 2 different prices for two different days, there will be at least 2 `<Rate>` blocks.</aside> |
| `EffectiveDate`<br>`ExpireDate` | Dates to define the time range of the `<Rate>`. We consider that one rate is applied for one night. <aside class="warning">The <code>ExpireDate</code> should not be the same as <code>EffectiveDate</code> The reservation would be considered a day-stay and would not be counted in occupancy.</aside> |
| `AmountAfterTax`<br>`CurrencyCode` | Amount for the given rate plan, room type, time period, and its currency (in <a href="https://en.wikipedia.org/wiki/ISO_4217" target="_blank">ISO 4217</a>). |
| `AgeQualifyingCode` | This block represents the number of people in the `<RoomStay>`. The `AgeQualifyingCode=10` is the number of adults (in `Count` value), and `AgeQualifyingCode=8` is the number of children. |
| `CountryName` | The only information we take from guests is their country of origin for segmentation analysis. |
