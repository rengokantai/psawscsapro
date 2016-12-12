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


##14. Managing Billing Strategies: EC2 Standard and Reserved Instances
###2 EC2 Instance Types
reserved instances:
- standard reserved instance: take a paticular VM or a paticular server and I expect to run this server 24/7/365.  you get a lower hourly rate in exchange for a commitment, and that commitment can either be a one-year commitment

- scheduled reserved instance: 


###3 EC2 instance in-depth
General purpose(GP) t2 m4 m3  
Compute optimized c3 c4  
memory optimized r3
storage optimized i2 d2  
gpu g2  

###4 Standard Reserved Instances Attributes
####02:16
__Instance type modifications are supported only for Linux__. Due to licensing differences Linux RIs cannot be modified to RedHat or SUSE

###3 EC2 instance in-depth



##15. Managing Billing Strategies: Consolidated Billing and Resource Groups









##16. Understanding CloudFormation, Elastic Beanstalk, and OpsWorks
###2 AWS CloudFormation

###3 Template Elements
####04:28
Stack Creation Errors
- You will be charged for resources provisioned even if there is an error.

###4 AWS Elastic Beanstalk
####03:45
Cloudformation vs elastic beanstalk
- CloudFormation supports Elastic Beanstalk
- Elastic Beanstalk does not provision CloudFormation templates





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

Recovery point objective(RPO)  
Theacceptable amount of data loss measured in time. For exxpple, if a disaster occurs at 12:00pm and the RPO is one hour, the system shouuld recober all data that was in the system before 11:00 AM. Data loss will span only one hour between 11:00 AM and 12:00 PM

####09:34
Databases
- RDS
- DynamoDB
- Redshift

Deployment and orchestration
- Cloudformation
- Elastic Beanstalk
- Opsworks









######99 Understanding AWS HA
import/export: large data sets:  
can be used to import to s3, glacier,ebs  
can be export from s3  
if bucket versioning is enabled only most recent version will be exported  

truecrypt

aws will wipe the device after downloading the data

aws will not destroy the device
###5 Automated Backup


Services with automated backups:
- RDS
- Elasticache
- Redshift

Services without automated backups
- EC2
RDS Automated Backup
- All Backups stored on S3
- MySQL DB engine only the innoDB storage engine is supported  
- MariaDB engine only the StraDB storage engine is supported
- __Delete a DB instance delete all automated backups__
- __ Manual snapshots are not deleted__
Ec2 backup overview 
- No automated backups
- Automated backups using CLI or python
- snapshots store in s3  
- snapshots are incremental, charge for incremental space  
- each snapshot still contains base snapshot data  


##19. Understanding AWS Data Pipeline and Integration with VMware
###2 AWS data pineline
AWS data pipeline
- A web service that helps you reliably process and move data between different AWS compute and storage services, as well as on-permises data sources, at specified intervals.  

Create ,access and manage using
- AWS Management console
- CLI
- SDKS
- Query API

supported compute services: 
- EC2 
- EMR  
supported services to store data: 
- dynamodb
- rds 
- redshift  


key concepts:
- Task runners
- Data nodes
- Activities
- Preconditions and actions


Data nodes  
Define the location and type of data that a pipeline activiey uses as inpyut ot output.
- A dynamoDB table that contains data for HiveActovoty or EmrActivity to use
- A MySQL table and database query that represents data for a pipeline activity to use
- A Amazon Redshift table that contains data for redshiftCopyActivity to use
- An Amazon  S3 location that contains one or more files for a pipeline activity to use


####Activities
A pipeline component that defines the work to perform  
AWS data pipeline procides pre-packaged activities such as moving data form one location to another or running hive queries
AWS data pipeline relies on amazon sns notifications as the primary way to indicate the status of pipelines and their components.



###3 Integration with VMWare
Use cases
- self-service aws portal with vCenter
- Migrate VMware VMs to Amazon EC2
- Leverage vCenter experience while getting started with AWS
- Reach new geographies from vCenter



