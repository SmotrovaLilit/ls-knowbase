# AWS Identity and Access Management (IAM)
- Uses to manage access to AWS services and resources
- Features:
	- IAM users, groups, and roles
	- IAM policies
	- Multi-factor authentication
	- IAM supports identity federation, which allows users with passwords elsewhere—like your corporate network or internet identity provider—to get temporary access to your AWS account.
- 💡 AWS is responsible for authentication/authorisation in AWS Cloud and in AWS services like amazon s3
- 💡 AWS is not responsible for authentication/authorisation in your application. 
	- IAM is not used for website authentication and authorization.
	- IAM  does not support security controls for protecting operating systems and networks.

## AWS account root user
- 💡 Do **not** use the root user for everyday tasks.
-  Use root user for tasks: changing your root user email address and changing your AWS support plan. see “Tasks that require root user credentials” in the [AWS Account Management Reference Guide](https://docs.aws.amazon.com/accounts/latest/reference/root-user-tasks.html).
## IAM users
- represents the person or application that interacts with AWS services and resources. It consists of a name and credentials.
- You define the user in your AWS account.
- by default users is without any permissions
- You can provide users with the following types of access:
	- Access to the AWS Management Console
		- name and password
	- Programmatic access to the AWS CLI and AWS API
		- set of access keys

## IAM policies
- is a document that allows or denies permissions to AWS services and resources.
- 💡 Follow the security principle of **least privilege** when granting permissions.
- 💡 You can apply IAM policies to IAM users, groups, or roles. 
- 💡 You cannot apply an IAM policy to the AWS account root user.
Example:
```json
{
"Version": "2012-10-17",
"Statement": [{
"Effect": "Allow",
"Action": "*",
"Resource": "*"
"Condition": {
	"StringNotEquals": {
	  "aws:ResourceAccount": [
		"222222222222"
	  ]
	}
}
}]
}
```
## IAM groups

- you can assign users to groups and assign policies to group
- groups cannot belong to groups
- users can belong to many groups.

## IAM ROLES
- 💡 is an identity that you can assume to gain temporary access to permissions.
- User can switch between roles to get permissions. 
- No static login credentials
- Are assumed programmatically
- Credentials are temporary for a configurable amount of time
- Credentials expire and rotated
- can be used for authentication applications(EC2 instances) in application-to-aws-service scenario
- roles also are used for federation scenarios, when you want to use corporate user accounts to get access to AWS console
## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 6
3.  [root user](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html).
4. https://explore.skillbuilder.aws/learn/course/external/view/elearning/1851/aws-technical-essentials?da=sec&sec=prep Module 1