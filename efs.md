EFS
---
![amazon efs](../images/efs.png)

- Amazon Elastic File System (EFS) provides simple, scalable, elastic file storage for use with AWS Cloud services and on-premises resources.
- When mounted on Amazon EC2 instances, an Amazon EFS file system provides a standard file system interface and file system access semantics, allowing you to seamlessly integrate Amazon EFS with your existing applications and tools.
- **Multiple Amazon EC2 instances can acess an Amazon EFS at the same time, allowing Amazon EFS to provide a common data source for workloads and applications running on more than one Amazon EC2 instance.**
- EFS도 S3와 비슷하게 storage class를 변경할 수 있는 lifecycle을 설정할 수 있지만,  최대 90일까지만 IA Storage로 트랜지션 할 수 있다.
- Example: there is a fleet of On-Demand EC2 instances that stores file doucments from the users to one of the attached EBS volumes. 
    - Problem: The system performance is quite slow because the architecture doesn't provide the EC2 instances a parellel shared access to the file documents.
    - Solution: Remember that an EBS volume can be attached to one EC2 instance at a time, hence, no ther EC2 instance can connect to that EBS Provisioned IOPS volume. **Take note as well that the type of storage needed here is a "file storage"** which means that S3 is not the best service to use because it is mainly used for "object storage", and **S3 does not provide the notion of "folders" too.**
    ※ ElastiCache is an in-memory data store that improves the performance of your applications, which is not what you need since it is not a file storage.