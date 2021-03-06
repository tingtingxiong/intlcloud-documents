### RI Matching Rules

After you purchase a Reserved Instance (RI), RI will be automatically matched with a pay-as-you-go instance within the validity period. Currently, RI only supports matching pay-as-you-go instances running on Linux. If there is no pay-as-you-go instance available for matching under your account, RI will be idle, but fees still incur. Eligible pay-as-you-go instances will be automatically matched immediately after purchase, and once the match is successful, the discount will take effect on the bill for the pay-as-you-go instance. 

- You cannot manually manage the matching relationship between RIs and pay-as-you-go instances.
- The RI billing method is well suited for instances that are used for up to 3,600 seconds per hour. You can run multiple instances at the same time, but you can only get a total of 3,600 seconds worth of RI discount per hour, and instance usage that exceeds 3,600 seconds per hour will be billed in an pay-as-you-go manner. 

For example, if you purchase a RI of model S3.16xlarge256 in Silicon Valley Zone 1, and three pay-as-you-go instances of model S3.16xlarge256 with the same attributes in the same availability zone are run for one hour each under the current account, then only one pay-as-you-go instance is billed for one hour at the RI price, and the other two instances are billed for 2 hours at the pay-as-you-go price. 

However, if you purchase a RI of model S3.16xlarge256 in Silicon Valley Zone 1, and run three pay-as-you-go instances (A, B, and C) with the same attributes in the same availability zone for 20 minutes each, then the total running time of the instances is one hour, and one hour of RI usage and 0 hours of pay-as-you-go usage is incurred. As shown in the figure below, those three instances are matched with the RI for 20 minutes each.

![1](https://main.qcloudimg.com/raw/a812f74455b8b9d8ebbc84e90e26bc04.png)

If three matching pay-as-you-go instances are running at the same time, the RI billing advantage is applicable to all the instances in one hour (up to 3,600 seconds); after that duration, they will be charged at the pay-as-you-go price.

![2](https://main.qcloudimg.com/raw/24926b2c2675e2d6959adcf62054f5b1.png)

#### Effective Time

The effective time of a RI is calculated on the hour. A RI takes effect at the dot of the hour before its the creation and is valid from the next hour for a full year; however, if the RI is created exactly at at the dot of the hour, its effective time and validity period are calculated based on that very hour.

For example, if you purchase and activate a RI at 13:25, the time period from 13:00 to 14:00 is eligible for the RI discount, and the validity period starts at 14:00 + 365*24.

For example, if you purchase a RI at 13:00, the RI discount can be enjoyed starting at 13:00, and the validity period is 13:00 + 365*24.

