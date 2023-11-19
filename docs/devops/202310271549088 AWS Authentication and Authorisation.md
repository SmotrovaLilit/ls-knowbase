# AWS Authentication and Authorisation
## EC2 application  to Amazon services 
For example EC2 to Amazon S3

- ⛔ You do not need to create IAM user for your application
- ⛔ Do not hardcode creadentials
- 💡 When you send a request to AWS service you must sign the request. It happens programmatically
- 💡Admin creates the role and assign permission to Amazon s3 bucket. He can create role for EC2 cases or Lambda or others. In our case for ec2
- 💡 You need to launch EC2 with Instance profile  to pass the IAM role to the EC2
- 💡 The Application in EC2 need to retrieve the IAM role temporary credentials  form EC2 and then make API call using these temporary credentials.
- The role can be assumed to many EC2 instances


## Users developers, admins to AWS console
💡 Admin creates users and groups and assigns users to group
💡 Users has name and password
💡 You can use federation to use your corporate accounts
💡 Admin creates polices and assigns them to users or groups
💡 Admin can enable MFA for users

## References
1. https://explore.skillbuilder.aws/learn/course/external/view/elearning/1851/aws-technical-essentials?da=sec&sec=prep Module 1
2. AWS user guide: [What Is IAM?(opens in a new tab)](https://docs.aws.amazon.com/en_us/IAM/latest/UserGuide/introduction.html)
3. AWS user guide: [IAM Identities (User, User Groups, and Roles)](https://docs.aws.amazon.com/en_us/IAM/latest/UserGuide/id.html)
4. AWS user guide: [Access Management for AWS Resources(opens in a new tab)](https://docs.aws.amazon.com/en_us/IAM/latest/UserGuide/access.html)
5. AWS user guide: [Security Best Practices in IAM(opens in a new tab)](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
6. AWS blog: [How to Create and Manage Users within AWS IAM Identity Center](https://aws.amazon.com/blogs/security/how-to-create-and-manage-users-within-aws-sso/)
