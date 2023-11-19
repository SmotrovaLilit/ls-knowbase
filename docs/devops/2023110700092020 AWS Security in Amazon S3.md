# AWS Security in Amazon S3

- everything is private by default
- you can make bucket and object public. Everyone can access public resources
- controlled access
	- IAM Polices [[2023102613345050 AWS Identity and Access Management (IAM)]]
		- cases
			- You have many buckets with different permission requirements. Instead of defining many different S3 bucket policies, you can use IAM policies.
			- You want all policies to be in a centralized location. By using IAM policies, you can manage all policy information in one location.
		- resource-based policies: access policies that you attach to your resources
		-  _user policie_**s**: access policies attached to users in your account.
	- S3 bucket policies
		- S3 bucket policies can only be attached to S3 buckets
		- S3 bucket policies specify what actions are allowed or denied on the bucket.
		- cases:
			- You need a simple way to do cross-account access to Amazon S3, without using IAM roles.
			- Your IAM policies bump up against the defined size limit. S3 bucket policies have a larger size limit.
- S3 encryption

## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 5
2. [Bucket Policy Examples(opens in a new tab)](https://docs.aws.amazon.com/en_us/AmazonS3/latest/userguide/example-bucket-policies.html)
3.  https://explore.skillbuilder.aws/learn/course/external/view/elearning/1851/aws-technical-essentials?da=sec&sec=prep Module 4
4. 