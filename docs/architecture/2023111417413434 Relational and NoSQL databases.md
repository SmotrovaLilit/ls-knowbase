# Relational and NoSQL databases
## Relational databases
✅ Complex SQL, clear relationships between your data
✅ Reduced redundancy. you don't need save the same data in different tables, you can use reference. 
✅ Familiarity
✅ ACID
⛔ Are not effective for storing unstructured data
⛔ Take more time to set up compared with NoSql
⛔ Difficult to scale
### Read-heavy systems horizontal scaling 
Solution: multiple read-only replicas with leader-follower replication. 
💡 Trade-off: between consistency and availability. Having more read servers leads to higher availability, but in turn, sacrifices data consistency (provided that the updates are asynchronous) since there is a higher chance of accessing stale data.  See [[202312141403055 Replication strategies]]
### Write-heavy systems  horizontal scaling 
Solutions:
- replicas and shards, but it’s a very challenging problem and makes for a highly complex database architecture. 

For example, in Postgres multi-master replication isn't supported by default. However, there are third-party solutions and plugins like BDR (Bi-Directional Replication) that provide the capability to set up multi-master replication for writes. However, setting up multi-master replication requires careful planning and consideration of how the system will work:
### Use cases:
- Applications that have a fixed schema and don't change often
- Applications that need a persistent storage and follow the ACID principle
	- ERP (Enterprise resource planning)
	- CRM(Customer relationship management)
	- Commerce and financial applications 
## NoSql databases
✅ Unstructured Data
✅ Horizontal Scaling
✅ Performance at large data volumes: NoSQL databases can be more efficient for both writing and reading operations when dealing with extensive data volumes, as they are often optimised to operate within distributed systems and handle parallel queries effective
⛔ Eventual Consistency

## References
1. [AWS course](https://explore.skillbuilder.aws/learn/course/external/view/elearning/1851/aws-technical-essentials?da=sec&sec=prep) Module 5
2. [System Design Interview Course](https://www.tryexponent.com/courses/system-design-interview/fundamentals-system-design/sql-nosql)
