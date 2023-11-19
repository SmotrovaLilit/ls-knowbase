# **Amazon Relational Database Service**  (RDS)

- hardware provisioning
- database setup 
- patching
- backups
- engines functions:
	- encryption at rest (protecting data while it is stored)
	- encryption in transit (protecting data while it is being sent and received).
- engines
	- Amazon Aurora
		- enterprise-class relational database
		- compatible with MySQL and PostgreSQL
		-  ✅ up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases.
		- ✅  replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.
	- PostgreSQL
	- Mysql
	- MariaDB
	- Oracle
	- Microsoft SQL Server
## Prof and cons
- ✅ Automatic HA and recovery provided
- ✅ Customer ownership of data
- ✅ Customer ownership of schema
- ✅ Customer control of network
- ⛔ Less throughput capabilities compare with NoSQL
##  Storage types
- General Purpose SSD (also called gp2 and gp3)
	- is best suited for development and testing environments
- Provisioned IOPS SSD (also called io1)
	- is best suited for productions environments
- Magnetic (also called standard)
	- for backward capability
## Backup data
- automated backups
	- by default
	- Retaining period: 0-35 days
	- opportunity for **Point-in-time recovery**
- manual snapshots
	- it is like Amazon EBS snapshots
	- they exist until you delete them
 💡 Use all options. Automated backups are beneficial for point-in-time recovery. With manual snapshots, you can retain backups for longer than 35 days.
## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 5
2. . https://explore.skillbuilder.aws/learn/course/external/view/elearning/1851/aws-technical-essentials?da=sec&sec=prep Module 5