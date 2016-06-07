#### psawscsapro
#####cp2
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
######92 Cloudfront, kinesis
Kinesis: data is stored 24 hours, can be increased to 7 days


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


