## Send Inventory

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
    <OTA_HotelInvCountNotifRQ xmlns="http://www.opentravel.org/OTA/2003/05">
      <Inventories HotelCode="45121140">
        <Inventory>
          <StatusApplicationControl Start="2017-05-01" InvTypeCode="King"/>
          <InvCounts>
            <InvCount CountType="1" Count="20"/>
            <InvCount CountType="2" Count="15"/>
            <InvCount CountType="4" Count="3"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-01" InvTypeCode="Deluxe"/>
          <InvCounts>
            <InvCount CountType="1" Count="13"/>
            <InvCount CountType="2" Count="10"/>
            <InvCount CountType="4" Count="1"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-02" InvTypeCode="King"/>
          <InvCounts>
            <InvCount CountType="1" Count="20"/>
            <InvCount CountType="2" Count="10"/>
            <InvCount CountType="4" Count="9"/>
            <InvCount CountType="5" Count="1"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-02" InvTypeCode="Deluxe"/>
          <InvCounts>
            <InvCount CountType="1" Count="13"/>
            <InvCount CountType="2" Count="5"/>
            <InvCount CountType="4" Count="6"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
      </Inventories>
    </OTA_HotelInvCountNotifRQ>
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
    <wsa:MessageID>unique-message-id</wsa:MessageID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelInvCountNotifRQ xmlns="http://www.opentravel.org/OTA/2003/05">
      <Inventories HotelCode="45121140">
        <Inventory>
          <StatusApplicationControl Start="2017-05-01" InvTypeCode="King"/>
          <InvCounts>
            <InvCount CountType="1" Count="20"/>
            <InvCount CountType="2" Count="15"/>
            <InvCount CountType="4" Count="3"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-01" InvTypeCode="Deluxe"/>
          <InvCounts>
            <InvCount CountType="1" Count="13"/>
            <InvCount CountType="2" Count="10"/>
            <InvCount CountType="4" Count="1"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-02" InvTypeCode="King"/>
          <InvCounts>
            <InvCount CountType="1" Count="20"/>
            <InvCount CountType="2" Count="11"/>
            <InvCount CountType="4" Count="8"/>
            <InvCount CountType="5" Count="1"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-02" InvTypeCode="Deluxe"/>
          <InvCounts>
            <InvCount CountType="1" Count="13"/>
            <InvCount CountType="2" Count="5"/>
            <InvCount CountType="4" Count="6"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
      </Inventories>
    </OTA_HotelInvCountNotifRQ>
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
    <wsa:MessageID>unique-message-id</wsa:MessageID>
    <wsa:To>https://api.pricematch.travel/htng_message</wsa:To>
  </soap:Header>
  <soap:Body>
    <OTA_HotelInvCountNotifRQ xmlns="http://www.opentravel.org/OTA/2003/05">
      <Inventories HotelCode="45121140">
        <Inventory>
          <StatusApplicationControl Start="2017-05-01" InvTypeCode="King"/>
          <InvCounts>
            <InvCount CountType="1" Count="20"/>
            <InvCount CountType="2" Count="16"/>
            <InvCount CountType="4" Count="2"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-01" InvTypeCode="Deluxe"/>
          <InvCounts>
            <InvCount CountType="1" Count="13"/>
            <InvCount CountType="2" Count="10"/>
            <InvCount CountType="4" Count="1"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-02" InvTypeCode="King"/>
          <InvCounts>
            <InvCount CountType="1" Count="20"/>
            <InvCount CountType="2" Count="11"/>
            <InvCount CountType="4" Count="8"/>
            <InvCount CountType="5" Count="1"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
        <Inventory>
          <StatusApplicationControl Start="2017-05-02" InvTypeCode="Deluxe"/>
          <InvCounts>
            <InvCount CountType="1" Count="13"/>
            <InvCount CountType="2" Count="5"/>
            <InvCount CountType="4" Count="6"/>
            <InvCount CountType="5" Count="2"/>
            <InvCount CountType="3" Count="0"/>
            <InvCount CountType="6" Count="0"/>
            <InvCount CountType="8" Count="0"/>
          </InvCounts>
        </Inventory>
      </Inventories>
    </OTA_HotelInvCountNotifRQ>
  </soap:Body>
</soap:Envelope>
```

The Hotel Inventory Count message provides the ability for a PMS to post inventory amounts.

We support the following inventory codes (CountType in the message body):

* `1` **Physical** - number of rooms/units physically existing on the property
* `2` **Definitive availability** - number of rooms/units available, minus number of allotments still available
* `3` **Tentative availability** - number of allotments still available
* `4` **Definitive sold** - number of rooms/units sold - status is confirmed
* `5` **Tentative sold** - number of rooms/units sold - status is option
* `6` **Out of order** - number of rooms/units temporarily unavailable (e.g. remodel, repair, etc.)
* `8` **Out of inventory** - number of rooms/units which are indefinitely unavailable (e.g. construction)

<aside class="warning">You must always use all the CountTypes 1, 2, 3, 4, 5, 6 and 8 in every message (even if Count = 0).</aside>

<aside class="notice">The resulting occupancy will be computed this way:<br>
<b>(Definitive sold + Tentative sold + Out of order) / (Physical - Out of inventory)</b></aside>

You should send an update for all the dates and room types modified after each inventory modification.

It is also required to send a full inventory update every 24 hours to correct any missed messages.

If it is not possible to send only the dates and room types modified, instead send a full update every hour (all room types, full horizon 365 days).

### Fields we consider

|  |  |
| --- | --- |
| `HotelCode` |  Maps the message to a specific property. You will receive the hotel code for each new property from BookingSuite. |
| `Inventory` | One `<Inventory>` block is given for one date and one room type of the inventory update.<aside class="notice">If 2 room types are updated, there will be at least 2 Inventory blocks. If 2 dates are updated, there will be at least 2 Inventory blocks.</aside> |
| `Start` | The stay date to be processed. The date format has to be YYYY-MM-DD |
| `InvTypeCode` | Room type code. |
| `InvCount` | One `<InvCount>` block defines the inventory count for one given status, for the considered date and room type.<br><br>The `CountType` defines the room status based on the list above.<br>The `Count` is the value of the updated inventory. |