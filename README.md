# CloudML
# Kinesis Key Concepts:

## What is a shard?
Shard is the base throughput unit of an Amazon Kinesis data stream. One shard provides a capacity of 1MB/sec data input and 2MB/sec data output. One shard can support up to 1000 PUT records per second. 
You will specify the number of shards needed when you create a data stream. For example, you can create a data stream with two shards. This data stream has a throughput of 2MB/sec data input and 4MB/sec data output, and allows up to 2000 PUT records per second. 
You can monitor shard-level metrics in Amazon Kinesis Data Streams and add or remove shards from your data stream dynamically as your data throughput changes by resharding the data stream.

