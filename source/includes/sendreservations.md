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
  <Body>
    <OTA_HotelResNotifRQ ResStatus="Commit" TimeStamp="2017-02-22T14:55:37Z">
      <HotelReservations>
        <HotelReservation CreateDateTime="2017-02-22T08:41:51.+03:00" ResStatus="Reserved">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="King">
                  <Rates>
                    <Rate EffectiveDate="2017-04-01" ExpireDate="2017-04-02" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="39.00" CurrencyCode="EUR"/>
                    </Rate>
                    <Rate EffectiveDate="2017-04-02" ExpireDate="2017-04-03" RateTimeUnit="Night" UnitMultiplier="1">
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
                        <CountryName Code="CRO"/>
                      </Address>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>
        </HotelReservation>
        <HotelReservation CreateDateTime="2017-02-22T08:41:51.+03:00" ResStatus="Reserved">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="CORP" RoomTypeCode="Deluxe">
                  <Rates>
                    <Rate EffectiveDate="2017-04-01" ExpireDate="2017-04-02" RateTimeUnit="Night" UnitMultiplier="1">
                      <Base AmountAfterTax="55.00" CurrencyCode="EUR"/>
                    </Rate>
                    <Rate EffectiveDate="2017-04-02" ExpireDate="2017-04-03" RateTimeUnit="Night" UnitMultiplier="1">
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
  <Body>
    <OTA_HotelResNotifRQ ResStatus="Modify" TimeStamp="2017-02-23T09:25:41Z">
      <HotelReservations>
        <HotelReservation CreateDateTime="2017-02-22T08:41:51.+03:00" ResStatus="Reserved">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="King">
                  <Rates>
                    <Rate EffectiveDate="2017-04-01" ExpireDate="2017-04-02" RateTimeUnit="Night" UnitMultiplier="1">
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
                        <CountryName Code="CRO"/>
                      </Address>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>
      </HotelReservations>
    </OTA_HotelResNotifRQ>
  </Body>
</Envelope>
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
  <Body>
    <OTA_HotelResNotifRQ ResStatus="Cancel" TimeStamp="2017-03-15T11:09:33Z">
      <HotelReservations>
        <HotelReservation CreateDateTime="2017-02-22T08:41:51.+03:00" ResStatus="Cancelled">
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
                <RoomRate NumberOfUnits="1" RatePlanCode="BAR" RoomTypeCode="King">
                  <Rates>
                    <Rate EffectiveDate="2017-04-01" ExpireDate="2017-04-02" RateTimeUnit="Night" UnitMultiplier="1">
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
                        <CountryName Code="CRO"/>
                      </Address>
                    </Customer>
                  </Profile>
                </ProfileInfo>
              </Profiles>
            </ResGuest>
          </ResGuests>
      </HotelReservations>
    </OTA_HotelResNotifRQ>
  </Body>
</Envelope>
```

This endpoint posts a new reservation creation, modification or cancellation to BookingSuite RateManager. The immediate response is a standard HTTP code (Ack / Nack).

Each OTA_HotelResNotifRQ message can contain up to 1000 reservations for a single hotel. These reservations are in a `<HotelReservation>` block, and must be gathered under the same transactional status.

### Fields we consider

|  |  |
| --- | --- |
| `<OTA_ResNotifRQ ResStatus=”Commit”/>` | Transactional status of the reservation. It can be:<br>- 'Commit' (creates a new reservation)<br>- 'Modify' (updates an existing reservation)<br>- 'Cancel' (cancels a reservation) |
| `<HotelReservation>` | Reservation block. We accept up to 1000 blocks. |
| `<HotelReservation CreateDateTime="2005-10-09T08:51:45 UTC">` | This is what we consider as the booking date. Please ensure the timezone matches that of the property. |
| `<HotelReservation ResStatus="Reserved">` | Reservation status. It can be:<br>- Reserved (confirmed reservation)<br>- Waitlisted(reservation on waitlist)<br>- In-House (in-house booking)<br>- Checked-Out (already checked-out reservation)<br>- Cancelled (already cancelled reservation) |
| `<UniqueID ID="3741"/>` | Unique reservation ID of the reservation that will permit us to link your message to the reservation in our database. |
| `<BasicPropertyInfo HotelCode="HXCAIZZ">` | The `Hotel Code` variable maps the message to a specific property. This code must be defined by you |
| `<CompanyName Code="OTA">WEB</CompanyName>` | We take this block as the source of the booking.<br>‘Code’ specifies the source (web, OTA, email, etc.), while the field is the general channel (Walk-in, WEB, TEL). |
| `<RoomStay>` | One `<Roomstay>` block is one room booked for the given reservation. |
| `<RoomStay MarketCode:"CORP">` | `MarketCode` is the intent of the stay, and what we take as segmentation data (leisure, corporate, etc). |
| `<RoomStay SourceOfBusiness="Booking.com">` | `SourceOfBusiness` is what we take as the agency. |
| `<RoomRate>` | One `<RoomRate>` block represents one rate for one rate plan and one room type.<aside class="notice">If the booking has 2 different room types, there will be at least 2 `RoomRate` blocks. If a booking has one room type, with 2 nights with a different rate plan, there will be 2 `RoomRate` blocks.</aside> |
| `<RoomRate RoomTypeCode="KING”>` | `RoomTypeCode` is the room type. It must match the `InvTypeCode` in inventory messages. |
| `<RoomRate RatePlanCode="RACK">` | `NumberOfUnits` is the number of rooms under the same roomtype and rate plan. |
| `<RoomRate NumberOfUnits="1">` | `NumberOfUnits` is the number of rooms under the same roomtype and rate plan. |
| `<Rate>` | One `<Rate>` block is for one amount for the given rate plan and room type for a given period.<aside class="notice">If the rate plan implies 2 different prices for two different days, there will be at least 2 `<Rate>` blocks.</aside> |
| `<Rate EffectiveDate="2006-01-12" ExpireDate="2006-01-15">` | Dates to define the time range of the `<Rate>`. We consider that one rate is applied for one night. <aside class="warning">The <code>ExpireDate</code> should not be the same as <code>EffectiveDate</code> The reservation would be considered a day-stay and would not be counted in occupancy.</aside> |
| `<Base AmountAfterTax="100.00" CurrencyCode="EUR"/>` | Amount rate for the given rate plan, room type, time period, and its currency (in <a href="https://en.wikipedia.org/wiki/ISO_4217" target="_blank">ISO 4217</a>). |
| `<AgeQualifyingCode="10" Count="2">` | This block represents the number of people in the `<RoomStay>`. The `AgeQualifyingCode=10` is the number of adults (in `Count` value), and `AgeQualifyingCode=8` is the number of children. |
| `<CountryName Code="UK"/>` | The only information we take from guests is their country of origin for segmentation analysis. |
