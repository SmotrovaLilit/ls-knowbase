# Multi region architecture
## When need
- an application need to be fast everywhere in the world
- an application need to be reliable like a google
- an application need to compliant with laws and regulations like GDPR [[2023080900305858 GDPR]]

## Advantages
- **Improved high availability**. If one region goes down, traffic can be routed to other
- **Disaster recovery and business continuity**.  If one region goes down, traffic can be routed to other in fast time. Companies has disaster recovery plan in that case.
- Reduced latency. 
- **Enhanced data redundancy and security**. Improve mitigating of risk of data loss, sensitive data can be stored in specific region to comply region regulations.
- **Compliance and risk management**. Hosting data in multiple regions helps to reduce risks associated with region specific legal and compliance issues.

## Regulatory compliance and the need for data homing and encryption
1. User's data is located in home country. 
	1. Proof of Concept
		1. ❌ We can't replicate user data  in another country. It means when country data center is failed, user can't login
		2. ❌ If user move to another country, for example from UK to Australia. His latency will increase because traffic must go form Australia to UK
2. ❌ Encryption
	1. This solution is raw yet

## Challenges of mutlti region architecture relates with:
- Handling different type of data
  - Metadata - non-personal data session data, tokens, data which is not contain identifiable information
  - Transient data - data which can contain personal information but is short-lived
  - Persistent data - data which can contain personal information and is long-lived
- Choosing the right distributed database
  - AWS Aurora
  - Google Cloud Spanner
  - CockroachDB,
  - YugaByte
  - other
- Sharding and replicating a database across regions
- Eventually consistent reads
- Data domiciling
- Monitoring
- Performance

## References
1. https://www.ory.dev/global-identity-and-access-management-multi-region/