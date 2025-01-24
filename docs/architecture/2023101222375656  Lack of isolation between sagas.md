# Lack of isolation between sagas
The isolation property of ACID transactions ensures that the outcome of executing multiple transactions concurrently is the same as if they were executed in some serial order.
## Anomalies
-  Lost updates. One saga overwrite data of another saga
- Dirty reads. One saga reads data of another saga that has not yet completed
-  Fuzzy/nonrepeatable reads. - Two different steps of a saga read the same data and get different results because another saga has made updates.

### Lost updates 
Example:
1. The first step of the Create Order Saga creates an Order.
2. While that saga is executing, the Cancel Order Saga cancels the Order.
3. The final step of the Create Order Saga approves the Order.

💡We can use READ FOR UPDATE and allow to cancel only approved orders. Solution depend on a business case.

###  Dirty reads
Cansel saga: 
1. ConsumerService—Increase the available credit.  
2. Order Service—Change the state of the Order to cancel. 
3. DeliveryService—Cancel the delivery.

Example of scenario:
1. CancelOrderSaga—Increase the available credit.
2. CreateOrderSaga—Reduce the available credit.
3. CancelOrderSaga—A compensating transaction that reduces the available credit.

Create Order Saga does a dirty read of the available credit
[[2023101300172828  Countermeasures for handling the lack of isolation]]

## References
1.  Microservices patterns by Chris Richardson, chapter 4.3