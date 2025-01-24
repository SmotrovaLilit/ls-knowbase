# Event Driven Architecture challenges 

## Receiver get OrderCanceled  before OrderCreated
### How to avoid this case
A common solution is to use sharded (partitioned) channels. Implemented  by modern message brokers like Apache Kafka and AWS Kinesis, 
- For message use key - order id. It guarantees that related order messages send to the same shards. 
- The message broker assigns each partition to an instance of the replicated receiver
![[Pasted image 20231012191500.png]]
Each event for a particular order is published to the same shard, which is read by a single consumer instance. As a result, these messages are guaranteed to be processed in order.
## Duplicate messages in at least once 
Use a message broker that preserves ordering when redelivering messages.

"An Order Created event followed by an Order Cancelled event for the same Order, and that somehow the Order Created event wasn’t acknowledged. The message broker should redeliver both the Order Created and Order Cancelled events. If it only 
redelivers the Order Created, the client may undo the cancelling of the Order."

- Write idempotent message handlers.
- Track messages and discard duplicates.
	- Use this if
		- application logic is not idempotent
		- or your message broker doesn’t preserve ordering when redelivering messages.
		- ![[Pasted image 20231012193539.png]]

## Transactional sending message

### Transactional outbox
https://microservices.io/patterns/data/transactional-outbox.html

### Message relay by implementing Polling publisher
https://microservices.io/patterns/data/polling-publisher.html
- 
- ✅ simple approach that works reasonably well at low scale
- ⛔ frequently polling the database can be expensive

### Message Relay by implementing  the transaction log tailing pattern
https://microservices.io/patterns/data/transaction-log-tailing.html

### Pros and cons
- ✅  Messages are guaranteed to be sent if and only if the database transaction commits
- ✅  Ordering message sending
- ⛔ Message publishes at least once.  
	- In case when Message relay crashes after sending message to broker. 

## References
1.  Microservices patterns by Chris Richardson, chapter 3 