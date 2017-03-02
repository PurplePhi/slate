## Development Process

### Roadmap

We usually develop with PMS partners by following this roadmap:

1. Scoping call after reading this documentation to confirm the process, answer any questions, and set development expectations
2. Development of inventory message (HotelInvCountNotifRQ)
3. Development of reservation message (HotelResNotifRQ) and group block messages (HotelInvBlockNotifRQ, optional)
4. Development of the rate update
5. Certification of the connection
6. Testing with live data from pilot property
7. Pilot testing with property
8. Defining procedures for new property set-up

### Certification process

Once development of both the 1-way and 2-way connections are complete, we will perform certification testing. This will check basic scenarios to see if messages are being sent correctly, and if the resulting data is valid for our system.

We will test the following scenarios:

* Create, modify, and cancel a single reservation 
* Create, modify, and cancel a group reservation
* Create, modify, and cancel a group block (optional)
* Push a single rate, and verify that the rate in the PMS is updated
* Push multiple rates, and verify that all selected rates in the PMS are updated
