# AWS Nonrelational databases

## Amazon DynamoDB

- key-value database service
- delivers single-digit millisecond performance at any scale
- ✅ DynamoDB is serverless
	- you do not have to provision, patch, or manage servers.
	- you do not have to install, maintain, or operate software.
- ✅ Auto scaling
- All user data stored in DynamoDB is fully encrypted at rest

## Prof and cons
- ✅ Key-value
- ✅ Massive throughput capabilities
- ✅ PB size potential
- ✅ Granular API access
- ⛔ Analytics more difficult compare with SQL
## Cases
- scalability problems with other traditional database systems
- OLTP workload.
- mission-critical application that must be highly available at all times without manual intervention
- high level of data durability, regardless of your backup-and-restore strategy.
## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 5
2. [**Amazon DynamoDB**(opens in a new tab)](https://aws.amazon.com/dynamodb/)
3. AWS developer guide: [What is Amazon DynamoDB?(opens in a new tab)](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)
4. AWS blog: [AWS Database Blog](https://aws.amazon.com/blogs/database/how-to-determine-if-amazon-dynamodb-is-appropriate-for-your-needs-and-then-plan-your-migration/)