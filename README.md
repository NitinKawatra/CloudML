# CloudML
#  OVERVIEW 

Kinesis is an infinitely scalable stream as a service that consists of shards. The service is commonly used due to its ease of use and low overhead alongside its competitive pricing. This is a common differentiator between Kinesis Streams and Kafka.
Like any managed service, Amazon Kinesis has some limitations you should be familiar with — and how to overcome these with scaling and throttling. It will be wise to leverage the AWS provided producers, consumers and available tools in order to leverage these best practices.

# Kinesis Key Concepts:

## What is a shard?
Shard is the base throughput unit of an Amazon Kinesis data stream. One shard provides a capacity of 1MB/sec data input and 2MB/sec data output. One shard can support up to 1000 PUT records per second. 
You will specify the number of shards needed when you create a data stream. For example, you can create a data stream with two shards. This data stream has a throughput of 2MB/sec data input and 4MB/sec data output, and allows up to 2000 PUT records per second. 
You can monitor shard-level metrics in Amazon Kinesis Data Streams and add or remove shards from your data stream dynamically as your data throughput changes by resharding the data stream.
