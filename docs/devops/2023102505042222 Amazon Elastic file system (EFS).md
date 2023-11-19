# Amazon Elastic file system (EFS)
Pros and cons:
- ✅  Multiple instances reading and writing simultaneously
- 💡Linux file system
- ✅ Regional resource: stores data in and across **multiple** Availability Zones.
- ✅ automatically scales
- ✅ HA
- ✅ on-premises servers can access Amazon EFS using AWS Direct Connect.


💡 Compared to block storage and object storage, file storage is ideal for use cases in which a large number of services and resources need to access the same data at the same time.

## Classes
-  Standard storage classes
-  EFS One Zone storage classes
	-  ideal for workloads that require the highest levels of durability and availability
	- ideal for workloads such as development, build, and staging environments.
## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 5