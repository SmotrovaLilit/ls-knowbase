#  Connectivity to AWS
## Amazon Virtual Private Cloud (Amazon VPC)

- allows to establish boundaries around your AWS resources
- allows to organise your resources into subnets
- to allow users form internet get resources you can attach an **internet gateway** to the VPC
- you can use virtual private gateway for private resources, it enables VPN connection between client and  virtual private gateway.
	- A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.
- you can use **AWS Direct Connect**  to establish a dedicated private connection between your data center and a VPC.

## Security
![[Pasted image 20231025151720.png]]
### Network ACLs
 - It checks a packet before packet  can enter into a subnet/exit from a subnet by indicating who sent the packet and how the packet is trying to communicate with the resources in a subnet.
 - Network ACLs is **stateless**
 - ACL check request response too because it doesn't remember state. 
 - By default:
	 -  default network ACL allows all inbound and outbound traffic
	 -  custom network ACL denies all inbound and outbound traffic
### Security group
- Controls inbound and outbound traffic for an Amazon EC2 instance.
- By default:
	- denies all inbound traffic and allows all outbound traffic. 
	- you can associate EC2 instances with the same security group or use different security groups for each instance.
- uses **stateful** packet filtering. They remember previous decisions made for incoming packets.
	- Security group remembers request and doesn't check response


## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 4