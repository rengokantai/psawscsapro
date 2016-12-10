# psawscsapro
##cp2
ELB characteristics:  
support ports:
- 25(smtp)
- 80/443
- 1024-65535
- does not suppoert EIP,public ip
- support zone apex (no www)
- support ipv4 and ipv6 (vpc only supports ipv4)
- one certificate per elb. multiple ssl cert require multiple elbs
- wildcard supported

######20 designing AWS Neworking
scaleup: increace instance size  
scaleout: add nats /subnets and migrate workloads,one subnet,one nat
######28 Designing AWS networking
You can extend on-promise DNS to aws vpc
You can not extend r53 to on-promise instances
cannot automatically register ec2 instances with private hosted zones

######85
```
Fn::Base64
```
(Condition Functions:)
```
Fn:::FindInMap
Fn::GetAtt
Fn::GetAZs
Fn::Join
Fn::Select
Ref
```



##17. Understanding CloudFront, Kinesis Streams, & SNS Mobile Push Notifications
###2 Cloudfront
####04:31 SSL
SNI Custom SSL: service name indicator







###4 Kinesis Streams
####04:14
Producers:
- Amazon Kinesis Streams API
- Amazon Kinesis Producer Library(KPL)
- Amazon Kinesis Agent


####05:23
Shards
- A uniquely identified group of data records in a stream
- A stream is composed of one or more shards, each of which provides a fixed unit of capacity
- Can support up to 5 transactions per second for reads
- Max total data read rate of 2MB/s
- Up to 1000 records per second for writes
- __Max total data write rate of 1MB/s (including partition keys)__



###6 SNS Mobile Notification
Publisher->AMazon SNS ->Push Notification Services->Subscriber  


##18. Understanding AWS High Availability and BC/DR Options
###2 RTO and RPO
Recovery time objective(RTO)  
THe time it takes after a disruption to restore a business process to its service level, as defined by the operational level agreement (OLA) For example, if a disaster accurs at 12:00 PM and the RTO is eight hours, the DR process should restore the business process to t he acceptable service level by 8:00pm











######99 Understanding AWS HA
import/export: large data sets:  
can be used to import to s3, glacier,ebs  
can be export from s3  
if bucket versioning is enabled only most recent version will be exported  

truecrypt

aws will wipe the device after downloading the data

aws will not destroy the device
######100
Ec2 backup overview  
snapshots store in s3  
snapshots are incremental, charge for incremental space  
each snapshot still contains base snapshot data
######103AWS data pineline
support: EC2 EMR  
services: dynamodb, rds redshift  
AWS data pipeline relies on amazon sns notifications as the primary way to indicate the status of pipelines and their components.



