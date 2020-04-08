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

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image1.png)

## How Import works:
Each import job uses a single Snowball appliance. After you create a job in the AWS Snowball Management Console or the job management API, we ship you a Snowball. When it arrives in a few days, you’ll connect the Snowball to your network and transfer the data that you want imported into Amazon S3 onto that Snowball using the Snowball client or the Amazon S3 Adapter for Snowball. When you’re done transferring data, ship the Snowball back to AWS, and we’ll import your data into Amazon S3.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image2.png)

## Export from Amazon S3
Choose what data you want to export from your S3 buckets for storage and compute workloads. AWS will load that data onto a device and ship it to you. When you're done ship the device back for erasing.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image3.png)

## How Export works:
Each export job can use any number of Snowball appliances. After you create a job in the AWS Snowball Management Console or the job management API, a listing operation starts in Amazon S3. This listing operation splits your job into parts. Each job part can be up to about 80 TB in size, and each job part has exactly one Snowball associated with it. After your job parts are created, your first job part enters the Preparing Snowball status.
Soon after that, we start exporting your data onto a Snowball. Typically, exporting data takes one business day. However, this process can take longer. Once the export is done, AWS gets the Snowball ready for pickup by your region's carrier. When the Snowball arrives at your data center or office in a few days, you’ll connect the Snowball to your network and transfer the data that you want exported to your servers by using the Snowball client or the Amazon S3 Adapter for Snowball.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image4.png)

## Local compute and storage only
Perform local compute and storage workloads, without transferring data. You can order multiple devices in a cluster for increased durability and storage capacity.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image5.png)

## Steps to create Import job in AWS Console:

Step1: Plan your job
Select destination country, select import into Amazon S3, and click on Next.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image6.png)

Step2: Give shipping details
Select an existing shipping address or add a new address, choose appropriate shipping speed based on your need, and provide tax information. Click Next after these details are filled correctly.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image7.png)

Step3: Give job details
Provide Job name, choose the type of device snowball or snowball edge(recommended) and provide the S3 bucket name where you would like to import the data. Click Next

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image8.png)

Step4: Set Security
Create or select an IAM role that snowball will assume to import data to Amazon S3.
Select the default AWS KMS key to encrypt your data. Click Next.
You can find below the policy document that specifies the permissions assigned to a role while creating it.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image9.png)

Step5: Set notifications
Create new SNS topic to receive job change status. Click Next

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image10.png)

Step6: Review
Review all the provided details and click on create job.

![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image11.png)

You can track the job status by clicking on the job on AWS console. Follow the instructions before you use snowball.

## How does a snowball look like?


![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image12.png)


![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image13.png)


![alt text](https://github.com/Nitink-aws/CloudML/blob/master/Image/Image14.png)
