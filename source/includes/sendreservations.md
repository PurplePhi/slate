## Send Reservations

> Request body

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

This endpoint posts a new reservation creation, modification or cancellation to BookingSuite RateManager. The immediate response is a standard HTTP code (Ack / Nack).

Each OTA_HotelResNotifRQ message can contain up to 1000 reservations for a single hotel. These reservations are in a `<HotelReservation>` block, and must be gathered under the same transactional status.

|  |  |
| --- | --- |
| [**TRY IT**](https://app.getpostman.com/run-collection/e6e6588af220c37af237) | [**SEE RESULT**](https://bookingsuite.revenue-management.travel/en/sandbox/data/reservations/8697f41528bf1356a3405c1ef0b2335f) |

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
| `<Base AmountAfterTax="100.00" CurrencyCode="EUR"/>` | Amount rate for the given rate plan, room type, time period, and its currency (in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)). |
| `<AgeQualifyingCode="10" Count="2">` | This block represents the number of people in the `<RoomStay>`. The `AgeQualifyingCode=10` is the number of adults (in `Count` value), and `AgeQualifyingCode=8` is the number of children. |
| `<CountryName Code="UK"/>` | The only information we take from guests is their country of origin for segmentation analysis. |