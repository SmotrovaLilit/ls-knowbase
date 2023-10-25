## Amazon elastic block store(EBS)
 Pros and cons:
 - ✅ Sizes up to 16 TiB
 - ✅  If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.
 - Solid states by default
 - HDD options
- ✅ incremental backups - Amazon EBS snapshots
- ✅ if you change fils you can reupload only changed block.
- ⛔  Availability Zone level resource
- ⛔ Stores data in a **single** Availability Zone.
- ⛔ Volumes do not automatically scale
- ⛔ Need to be in the same availability zone to attach to EC2 instances


## References
1. [https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials](https://explore.skillbuilder.aws/learn/course/134/play/85854/aws-cloud-practitioner-essentials) Module 5