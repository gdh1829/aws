Dynamo DB
===
- NoSQL database service that provides fast and predictable performance with seamless scalability.
- Offers **encyrption at rest**
- You can create database tables that can store and retrieve any amount of data, and serve any level of request traffic
- You can **scale up or scale down your tables' throughput capacity without downtime or performance degradation**, and use the AWS Management Console to monitor resource utilization and performance metrics.
- Provides **on-demand backup capability** as well as enable **point-in-time recovery** for your DynamoDB tables. With point-in-time recovery, you can restore that table to any point in time during the __last 35 days__.
  - on-demand backups are available at no additional cost beyond the normal pricing that's associated with backup storage size.
  - on-demand backups **cannot copies to a different account ro Region**. To reate backup copies across AWS accounts and Regions and for other advanced featrues, you should use **AWS Backup**.
- All of your data is stored in partitions, backed by solid state disks (SSDs) and **automatically replicated across multiple AZs in an AWS region**, providing built-in high availablity and data durability.
- You can create **tables that are automatically replicated across two or more AWS Regions, with full support for multi-master writes.**
- supports DynamoDB **Gateway endpoint** not interface endpoint.

## Core Components
- __Table__: a collection of items
    - DynamoDB stores data in a table, which is a collection of data
    - Are schemaless
    - initial limit of **256 tables per region**
- __Items__: a collection of attributes
    - DynamoDB uses __primary keys__ to uniquely identify each item in a table and __secondary indexes__ to provide more querying flexibility
    - Each table contains zero or more items
- __Attribute__: a fundamental data element
    - DynamoDB supports nested attributes **up to 32 levels deep**.
- __Primary Key__: uniquely identifies each item in the table, so that no two items can have the same key. Must be scalar
    - __Partition key__: a simple primary key, composed of one attribute
    - __Partition key and short key__ (_composite primary key_): composed of two attributes
    - DynamoDB uses the partition key value as input to an internal hash function. The output from the hash function determines the partition in which the item will be stored. All items with the same partition key are stored together, in sorted order by sort key value. If no sort key is used, no two items can have the same partition key value.
- __Secondary Indexes__: lets you query the data in the table using an alternate key, in addition to queries against the primary key.
    - You can create one or more secondary indexes on a table.
    - Two kinds of indexes:
        - __Global secondary index (GSI)__: An index with a partition key and sort key that can be differnt from those on the table
        - __Local secondary index (LSI)__: An index that has the same partition key as the table, but a different sort key
    - You can define up to 5 global secondary indexes and 5 local secondary indexes per table.

## DynamoDB Streams: 
- an **optional feature** that captures data modification events in DynamoDB tables. 옵셔널 기능이므로 기본적으로 비활성 상태. 사용을 위한 활성화 반드시 필요.
- 다이나모DB 테이블 아이템 변경에 대한 **정렬된 정보 흐름(ordered flow of information)**.
- 애플리케이션이 테이블에 생성/변경/삭제 아이템을 발생시킬때마다, 다이나모DB 스트림즈는 변경된 아이템의 primary key 속성이 포함된 스트림 레코드를 작성한다. 이 스트림 레코드는 다이나모디비 테이블의 각 아이템의 데이터 변경사항에 대한 정보를 담고 있다. 또한 스트림 레코드가 추가적 정보를 캡쳐하도록 설정 또한 가능하다. ex 수정된 아이템의 'before'와 'after' 이미지.
- AWS 람다와 통합하여 다이나모디비 스트림즈의 이벤트에 자동으로 반응하는 trigger도 생성할 수 있다. 이 트리거로 다이나모디비 테이블 데이터 변경에 반응하는 애플리케이션도 만들 수 있다. 람다와 스트림 ARN을 엮어놓으면, 즉시 테이블에 변경사항이 생겼을때 테이블 스트림에 새로운 스트림 레코드가 등록되고 람다는 해당 스트림을 polling하여 동기적으로 람다 함수를 동작시킨다.
- The naming convention for DynamoDB Streams endpoints is _streams.dynamodb..amazonaws.com_
- Each event is represented by a _stream record_, and captures the following events:
    - A new item is added to the table: captures an image of the entire item, including all of its attributes.
    - An item is updated: captures the "before" and "after" image of any attributes that were modified in the item.
    - An item is deleted from the table: captures an image of the entire item before it was deleted.
- Each stream record also contains the name of the table, the event timestamp, and other metadata
- Stream records are organized into groups, or __shards__. Each shard acts as a container for multiple stream records, and contains information required for accessing and iterating through these records.
- Stream records have a **lifetime of 24 hours**; after that, they are automatically removed from the stream.
- You can use **DynamoDB Streams together with AWS Lambda to create a _trigger_**, which is a code that executes automatically whenever an event of interest appears in a stream.
- DynamoDB Streams enables powerful solutions such as **data replication within and across Regions**, **materialized views of data in DynamoDB tables**, **data analysis using Kinesis materialized views**, and much more.
![dynamodb_streams](./images/dynamodb_streams.png)
![dynamodb_stream_with_triggers](./images/dynamodb_stream_with_trigger.png)

## DAX - DynamoDB Accelerator
- fully managed, highly available, in-memory cache for DynamoDB that delivers up to a 10x performance improvement (millisec -> microsec event at millions of requests per second)
- **does all the heavy lifting required to add in-memory acceleration to your DynamoDB tables, without requiring developers to manage cache invalidation, data population, or cluster management.**

## Auto Scaling
- not enabled by default
- manually set maximum provisioned read and write capacity, target utilization.

## Data Types for Attributes
- __Scalar Types__
    - A scalar type can represent exaclty one value. 
    - The scalar types are number, string, binary, Boolean, and null.
    - Primary keys should be scalar types.
- __Document Types__
    - A document type can represent a complex structure with nested attributes.
    - such as you would find in a JSON document. 
    - The document types are list and map.
- __Set Types__
    - A set type can represent multiple scalar values.
    - The set types are string set, number set, and binary set.

## Throughput Management
- DynamoDB **auto scaling**
    - Define a range (upper and lower limits) for __read and write capacity units__, and define a target utilization percentage within that range.
    - A table or a global secondary index can increase its __provisioned read and write capacity__ to handle sudden increases in traffic, without request throttling.
    - DynamoDB auto scaling can decrease the throughput when the workload decreases so that you don't pay for unused provisioned capacity.
- **Provisioned throughput**
    - manually defined maximum amount of capacity that an application can consume from a table or index. If your application exceeds your provisioned throughput settings, **it is subject to request throttling**.
- **Reserved capacity**
    - with reserved capacity, you pay a **one-time upfront fee** and commit to a **minimum usage level** over a period of time, for cost-saving solutions.

## Throttling
- _Throttling_ prevents your application form consuming too many capacity units. DynamoDB can throttle read or write requests that exceed the throughput settings for a table, and can also throttle read requests exceeds for an index
- When a request is throttled, it fails with an __HTTP 400__ code (Bad Request) and a `provisionedThroughputExceededException`

## Other Notes
- When you read data from a DynamoDB table, the response might not reflect the results of a recently completed write operation. The response might include some stale data, but you should __eventually have consistent reads__.
- When you request a __strongly consistent read__, DynamoDB returns a response with the most up-to-date data, reflecting the updates from all prior write operations that were successful. A stongly consistent read might not be available if there is a network delay or outage.
- DynamoDB **does not support stongly consistent reads across AWS regions**
- When you create a table or index in DynamoDB, **you must specify your throughput capacity requirements for read and write activity** in terms of:
    - One __read capacity unit__ represents one stongly consistent read per second, or two eventually consistent reads per second, for an item **up to 4 KB in size**. If you need to read an item that is larger than 4 KB, DynamoDB will need to consume additional read capacity units.
    - One __write capacity unit__ represents one write per second for an item **up to 1 KB in size**. If you need to write an item that is larger than 1 KB, DynamoDB will need to consume additional write capacity units.