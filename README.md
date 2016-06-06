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
