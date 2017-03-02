# Sandbox

The sandbox gives you a safe place to send and view messages for testing purposes.

The following information will be provided upon the start of development:

* **Message Credentials (Username & Password)**: These are unique per PMS
* **Hotel Code**: This is a sample hotel code that permits you to route messages to your specific sandbox environment
* **Sandbox URL**: This will redirect you to the sandbox (messages received; their responses; reservations that are saved; resulting inventory/occupancy)

<aside class="notice">If you did not receive your sandbox information, please request it at bookingsuite.connectivity@booking.com</aside>

## Using the sandbox

Your sandbox consists of two main sections: Reservations/Inventory and Rates push.

![sandbox](/images/sandbox/1.png)

Depending on your agreement with BookingSuite, the Rates push tab may be disabled at first. It can be activated later when needed by contacting bookingsuite.connectivity@booking.com, or via the Help button in the lower-left corner of the screen.

The following articles will explain the individual sections within each tab.

## Messages received

Every message you send to our endpoint (https://api.pricematch.travel/htng_message) will appear here. This requires having the correct username and password in the SOAP header of the message.

![sandbox](/images/sandbox/2.png)

The last 10 messages received are sorted here by timestamp in descending order. You can download each message by clicking on its name. You will also be able to see any errors appearing in the messages with a brief explanation.

![sandbox](/images/sandbox/3.png)

## Reservations

The Reservations view lists the reservations sent via OTA_HotelResNotifRQ, sorted in descending order by modified date. Here you can see core information that we collect from each reservation: 

* A unique reservation ID
* Check-in date
* Check-out date
* Booking date
* Price
* Room type
* Number of reservations 
* Status of the reservation (confirmed or cancelled)

The default currency for your sandbox hotel is set to the Euro (EUR). Please let us know if you wish to change this default currency to another type. Any reservations with prices besides the default currency will automatically be converted without issue.

![sandbox](/images/sandbox/4.png)

During the development of reservation messages, it is useful to check them in the sandbox to see whether the information that we are displaying matches what you sent to the platform.

If you wish to start over at any point, you can delete all reservations by clicking on the “Delete reservations” button at the top of the list.

## Inventory

The inventory tab will show you the result of the hotel_inv_count_notif message. The inventory messages should reflect the changes in the reservation messages, so please make sure that both tabs are updated with every new reservation.

The default sandbox test hotel has 100 rooms, and your inventory messages should be based on that amount. The Inventory view will show you the room-nights for the next 30 days for all room types, divided into each CountType that we use.

![sandbox](/images/sandbox/5.png)

If you wish to start over at any point, you can delete the entire inventory by clicking on the “Delete
Inventory” button at the top of the list.

## Final occupancy

The Final occupancy tab will display the end result of the reservations and inventory messages received. Once you have successfully sent both message types, check Final occupancy to see if there are any discrepancies. Usually if something is wrong, it will be most noticeable in the occupancy percentages (i.e. over 100%, negative numbers, etc.).
<aside class="notice">Occupancy is calculated by the following formula:<br>
<b>(Definitive sold + Tentative sold + Out of order) / (Physical - Out of inventory)</b></aside>

![sandbox](/images/sandbox/6.png)

## Codes Mapping

The Codes Mapping tab is used for setting up the rate pushes in a 2-way connection. You will be able to add the URL, username, password and hotel code for messages. Don't forget to tick the "Connect to channel manager" option - this will enable the 2-way connection. In this context, “channel manager” refers to the system that receives the rate push, which can be a PMS or channel manager.

![sandbox](/images/sandbox/7.png)

Beneath that, you will find 4 test room/rate types that would correspond to the "calendar view" in our product: a double room, a single room, a suite and a family room - all set to breakfast not included, refundable rate. Click on the blue plus sign to add mapping for these rooms.

![sandbox](/images/sandbox/8.png)

Mapping can be done for multiple room types, rates and occupancies. Below is an example of a
mapping for two different rate plans for the same room type:

![sandbox](/images/sandbox/9.png)

In this example, a rate push from the RateManager calendar view will update two rates: the base rate (BB-GR), and an additional rate (HB-GR) which will always be 10% higher than the base rate.

## Send rates

The RateManager platform will calculate rate recommendations for each of the next 360 days for the room/rate combinations set in each calendar view. The property can choose to update their rates based on these recommendations manually, as individual rates for specific dates, or in batches. There is also an autopilot feature that can be enabled, which pushes new rates every 4 hours based on pre-set rules defined by the property.
<aside class="warning">Autopilot can push a large amount of rates at once, so please ensure that RateManager has permission in your system to perform these actions (anti-flooding policies, etc.).</aside>

The Send rates tab in your sandbox mimics the manual update feature for testing. With a live property, the property owner will be triggering rate updates.

Once you have set everything up under Codes Mapping, you can begin to test sending rates. You can choose a date and room type, then set a price.

![sandbox](/images/sandbox/10.png)

You can send rates one by one, or queue up several of them by clicking on the blue plus sign. 

![sandbox](/images/sandbox/11.png)

<aside class="notice">Please note that you have to add rates to the queue before sending them (even if only sending one rate).</aside>

You can view the results of the rates you sent in the channel manager logs.

![sandbox](/images/sandbox/12.png)

If you have any questions, or sandbox adjustment requests, please contact us at bookingsuite.connectivity@booking.com or via the Help button in the lower-left corner of the screen.