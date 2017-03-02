## Conventions

### 1-way, 2-way

We define connectivity as 1-way or 2-way.

1-way refers solely to data transfer from your PMS to RateManager. This means that we will only be able to receive data from your system. It looks something like this:

![diagram](/images/connectivity_1way.jpg)

2-way refers to data transfer from your PMS to RateManager, and RateManager rate updates back to your PMS. It looks something like this:

![diagram](/images/connectivity_2way.jpg)

### Reservation data

Reservation data refers to all the data linked to a booking, any or all of which can impact the occupancy of a property. To make sure RateManager has everything it needs, please provide all information regarding sold rooms, as well as out-of-order/out-of-inventory rooms. Please do not send dummy rooms, nor any guest or property personal data, as these are not used by RateManager.

The most basic functions of our RateManager product are dependent on computing the right occupancy and revenue, which is based on the data you provide us with. We need at least the following information per booking:

* a unique reservation ID to identify the booking, and update it if needed
* a check-in and check-out date
* a booking date
* a status indicator, at least for cancellations, that has an impact on the final occupancy
* an average rate. We recommend providing the exact rate per night, to avoid discrepancies between your reports and the ones we provide

However, in addition to this core data, RateManager can also analyze additional segmentation data to provide more nuanced recommendations. By providing all information requested in this specification, we can provide the maximum benefits of RateManager to our mutual customers. 

### Property set-up process

Once the interface has been completed between RateManager and your PMS, we will be using a standardized process to set-up RateManager for new properties.

It is important to understand that we use a property’s historical data to train our algorithm for that specific property. To this end, for each property set-up, a complete history of 2 years will be requested from you. This historical data will only be requested once, at the beginning of set-up. Afterwards, we will only need to update new data as it comes in.

The property set-up process will usually be the following:

1. Make the necessary configurations, depending of the methods and conventions used (hotel code mapping, FTP access, username and password set-up)
2. PMS sends the property’s historical data of the last 2 years to RateManager
3. PMS sends current data to RateManager, then activates live synchronization
