# Countermeasures for handling the lack of isolation
-  Semantic lock
- Commutative updates - Design update operations to be executable in any order
- Pessimistic view - Reorder the steps of a saga to minimize business risk
- Reread value - Prevent dirty writes by rereading data to verify that it’s unchanged before overwriting it. See [Optimistic Offline Lock pattern](https://martinfowler .com/eaaCatalog/optimisticOfflineLock.html)
	- Reread data before update and return error if data is updated
- Version file - Record the updates to a record so that they can be reordered.
- By value - Use each request’s business risk to dynamically select the concurrency mechanism.
	- If risk valuable than use distributed transactions, another way use other countermeasures.
##  Countermeasure Semantic lock
- Saga’s compensatable transaction sets a flag in any record that it creates or updates. The flag indicates that the record isn’t committed and could potentially change.  You can use status. 
- Other transactions must consider records with semantic lock. For example, if a service gets the command cancelOrder and the order is creating concurrently, you need in cancelOrder handler either return error,  either wait until the order is created.
	- ⛔ in case if an application returns error: client must implement retrying mechanism
	- ⛔ in case when an application waits of completing order creation saga: an application must implement deadlock detection algorithm that performs a rollback of a saga to break a deadlock and reexecute it. 
## Countermeasure Pessimistic view 
### Example of dirty read:
Cansel saga: 
1. ConsumerService—Increase the available credit.  
2. Order Service—Change the state of the Order to cancelled. 
3. DeliveryService—Cancel the delivery.

Example of scenario:
1. CancelOrderSaga—Increase the available credit.
2. CreateOrderSaga—Reduce the available credit.
3. CancelOrderSaga—A compensating transaction that reduces the available credit.

Create Order Saga does a dirty read of the available credit
### The solution
1. Order Service—Change the state of the Order to cancelled.
2. DeliveryService—Cancel the delivery.
3. CustomerService—Increase the available credit.

This order eliminates the possibility of a dirty read.
## References
1.  Microservices patterns by Chris Richardson, chapter 4.3