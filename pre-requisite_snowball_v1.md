# Snowball create job parameters:

## Create_job (**kwargs)

## Creates a job to import or export data between Amazon S3 and your on-premises data center. Your AWS account must have the right trust policies and permissions in place to create a job for Snowball.

Parameters 
* JobType (string) -- Defines the type of job that you're creating.

* Resources (dict) --
Defines the Amazon S3 buckets associated with this job.
With IMPORT jobs, you specify the bucket or buckets that your transferred data will be imported into.
With EXPORT jobs, you specify the bucket or buckets that your transferred data will be exported from. Optionally, you can also specify a KeyRange value. If you choose to export a range, you define the length of the range by providing either an inclusive BeginMarker value, an inclusive EndMarker value, or both. Ranges are UTF-8 binary sorted.

* S3Resources (list) --
   An array of S3Resource objects.

* (dict) --
Each S3Resource object represents an Amazon S3 bucket that your transferred data will be exported from or imported into. For export jobs, this object can have an optional KeyRange value. The length of the range is defined at job creation, and has either an inclusive BeginMarker , an inclusive EndMarker , or both. Ranges are UTF-8 binary sorted.

* BucketArn (string) --
      The Amazon Resource Name (ARN) of an Amazon S3 bucket.
* KeyRange (dict) --
For export jobs, you can provide an optional KeyRange within a specific Amazon S3 bucket. The length of the range is defined at job creation, and has either an inclusive BeginMarker , an inclusive EndMarker , or both. Ranges are UTF-8 binary sorted.
* BeginMarker (string) --
The key that starts an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.
* EndMarker (string) --
The key that ends an optional key range for an export job. Ranges are inclusive and UTF-8 binary sorted.
* LambdaResources (list) --
   The Python-language Lambda functions for this job.
* (dict) --
      Identifies
* LambdaArn (string) --
An Amazon Resource Name (ARN) that represents an AWS Lambda function to be triggered by PUT object actions on the associated local Amazon S3 resource.
* EventTriggers (list) --
The array of ARNs for S3Resource objects to trigger the LambdaResource objects associated with this job.
> (dict) --
      The container for the EventTriggerDefinition$EventResourceARN .
* EventResourceARN (string) --
The Amazon Resource Name (ARN) for any local Amazon S3 resource that is an AWS Lambda function's event trigger associated with this job.
* Ec2AmiResources (list) --
   The Amazon Machine Images (AMIs) associated with this job.
* (dict) --
A JSON-formatted object that contains the IDs for an Amazon Machine Image (AMI), including the Amazon EC2 AMI ID and the Snowball Edge AMI ID. Each AMI has these two IDs to simplify identifying the AMI in both the AWS Cloud and on the device.
* AmiId (string) -- [REQUIRED]
      The ID of the AMI in Amazon EC2.
* SnowballAmiId (string) --
      The ID of the AMI on the Snowball Edge device.
* Description (string) -- Defines an optional description of this specific job, for example Important Photos 2016-08-11 .
* AddressId (string) -- The ID for the address that you want the Snowball shipped to.
* KmsKeyARN (string) -- The KmsKeyARN that you want to associate with this job. KmsKeyARN s are created using the CreateKey AWS Key Management Service (KMS) API action.
* RoleARN (string) -- The RoleARN that you want to associate with this job. RoleArn s are created using the CreateRole AWS Identity and Access Management (IAM) API action.
* SnowballCapacityPreference (string) -- If your job is being created in one of the US regions, you have the option of specifying what size Snowball you'd like for this job. In all other regions, Snowballs come with 80 TB in storage capacity.
* ShippingOption (string) --
The shipping speed for this job. This speed doesn't dictate how soon you'll get the Snowball, rather it represents how quickly the Snowball moves to its destination while in transit. Regional shipping speeds are as follows:
* In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day.
* In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way.
* In India, Snowballs are delivered in one to seven days.
* In the US, you have access to one-day shipping and two-day shipping.
* Notification (dict) --
Defines the Amazon Simple Notification Service (Amazon SNS) notification settings for this job.
* SnsTopicARN (string) --
The new SNS TopicArn that you want to associate with this job. You can create Amazon Resource Names (ARNs) for topics by using the CreateTopic Amazon SNS API action.
You can subscribe email addresses to an Amazon SNS topic through the AWS Management Console, or by using the Subscribe AWS Simple Notification Service (SNS) API action.
* JobStatesToNotify (list) --
The list of job states that will trigger a notification for this job.
* (string) --
* NotifyAll (boolean) --
Any change in job state will trigger a notification for this job.
* ClusterId (string) -- The ID of a cluster. If you're creating a job for a node in a cluster, you need to provide only this clusterId value. The other job attributes are inherited from the cluster.
* SnowballType (string) --
The type of AWS Snowball device to use for this job. Currently, the only supported device type for cluster jobs is EDGE .
For more information, see Snowball Edge Device Options in the Snowball Edge Developer Guide.
* ForwardingAddressId (string) -- The forwarding address ID for a job. This field is not supported in most regions.
* TaxDocuments (dict) --
The tax documents required in your AWS Region.
* IND (dict) --
The tax documents required in AWS Regions in India.
* GSTIN (string) --
The Goods and Services Tax (GST) documents required in AWS Regions in India.
Return type
dict
Returns
Response Syntax
{
    'JobId': 'string'
}

Request Syntax
response = client.create_job(
    JobType='IMPORT'|'EXPORT'|'LOCAL_USE',
    Resources={
        'S3Resources': [
            {
                'BucketArn': 'string',
                'KeyRange': {
                    'BeginMarker': 'string',
                    'EndMarker': 'string'
                }
            },
        ],
        'LambdaResources': [
            {
                'LambdaArn': 'string',
                'EventTriggers': [
                    {
                        'EventResourceARN': 'string'
                    },
                ]
            },
        ],
        'Ec2AmiResources': [
            {
                'AmiId': 'string',
                'SnowballAmiId': 'string'
            },
        ]
    },
    Description='string',
    AddressId='string',
    KmsKeyARN='string',
    RoleARN='string',
    SnowballCapacityPreference='T50'|'T80'|'T100'|'T42'|'T98'|'NoPreference',
    ShippingOption='SECOND_DAY'|'NEXT_DAY'|'EXPRESS'|'STANDARD',
    Notification={
        'SnsTopicARN': 'string',
        'JobStatesToNotify': [
            'New'|'PreparingAppliance'|'PreparingShipment'|'InTransitToCustomer'|'WithCustomer'|'InTransitToAWS'|'WithAWSSortingFacility'|'WithAWS'|'InProgress'|'Complete'|'Cancelled'|'Listing'|'Pending',
        ],
        'NotifyAll': True|False
    },
    ClusterId='string',
    SnowballType='STANDARD'|'EDGE'|'EDGE_C'|'EDGE_CG'|'EDGE_S',
    ForwardingAddressId='string',
    TaxDocuments={
        'IND': {
            'GSTIN': 'string'
        }
    }
)

