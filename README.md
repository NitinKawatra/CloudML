# CloudML
##	Overview

Snowball is a petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of the AWS cloud. Using Snowball addresses common challenges with large-scale data transfers including high network costs, long transfer times, and security concerns.

When planning on getting your data into the cloud as a part of an application migration or a data center shutdown, you will run into the hard limits of data transport. When your Internet speeds are not enough to keep up with your data migration plan, it’s time to consider AWS Snowball. The Snowball appliance allows you to move archives, data lakes, and whatever data you have at faster-than Internet speeds right into Amazon S3 buckets. From Amazon S3, data can be archived into Glacier or analyzed by other services such as AWS Redshift or EMR. This implementation guide will get you started with AWS Snowball's quick, simple, and secure process for migrating large amounts of data into AWS.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Architecture.png)
  
## What you'll accomplish?

Create a data import job using the AWS Console. Afterwards, AWS will prepare and ship a Snowball appliance to the address you specified.
Transfer your data onto the Snowball using the client. Then ship the Snowball back to AWS. The integrated E-Ink label on the Snowball makes this easy for you by automatically updating with the return address. There is no packaging necessary, as the Snowball is its own shipping container.
See your data securely imported into the cloud and stored in Amazon S3. When we receive the Snowball from you, we will import your data into Amazon S3 buckets. After the import is completed, the appliance is erased for your protection in accordance with NIST media sanitation standards.

with the return address. There is no packaging necessary, as the Snowball is its own shipping container.
See your data securely imported into the cloud and stored in Amazon S3. When we receive the Snowball from you, we will import your data into Amazon S3 buckets. After the import is completed, the appliance is erased for your protection in accordance with NIST media sanitation standards.

## Estimating Monthly Costs:

Snowball pricing has four main cost components: 

(1) a service fee for each job you run, 

(2) data transfer fees from Amazon S3, 

(3) the shipping costs to transport a Snowball appliance to and from your address, and 

(4) the number of days you keep Snowball onsite.

The total cost of moving your data into AWS will vary depending on the amount. There is a service charge of $250 for the appliance and an overage penalty of $15/day if you keep it for more than 10 days. Data transfers into Amazon S3 are free. Shipping charges are based on your location and your carrier.
Example: Let's say you want to import 10 TB into the US East Region. A 50 TB Snowball device would cost $200 for the first 10 days, and $15 days thereafter. So, the Snowball import cost for 10 TB would be a onetime $200 (assuming 10 days or fewer). Data transfer-in would be $0.00 (free). Additional charges including S3 requests made during the import and monthly charges for S3 Standard will apply. These charges will vary based on the number of objects and Region used. The shipping cost would be variable depending on your location.


##	Types of Snowball jobs
## Import into Amazon S3
AWS will ship an empty device to you for storage and compute workloads. You'll transfer your data onto it and ship it back. After AWS gets it, your data will be moved.

## How Import works:
Each import job uses a single Snowball appliance. After you create a job in the AWS Snowball Management Console or the job management API, we ship you a Snowball. When it arrives in a few days, you’ll connect the Snowball to your network and transfer the data that you want imported into Amazon S3 onto that Snowball using the Snowball client or the Amazon S3 Adapter for Snowball. When you’re done transferring data, ship the Snowball back to AWS, and we’ll import your data into Amazon S3.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Architecture.png)
