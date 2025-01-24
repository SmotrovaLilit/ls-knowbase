# Asynchronous communication vs synchronous communication

| synchronous communication                                                                                                                                                                                                                                | asynchronous communication |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| ⛔ Each additional service involved in processing a request decreases availability.                                                                                                                                                                       | ✅ Don't decrease availability|
| ✅ Easiest to use                                                                                                                                                                                                                                         |⛔ Difficult to use, some service may not support asynchronous communication|
| 💡 You must implement timeouts when executing requests, limit the count of out-standing requests, and use the Circuit Breaker design pattern to prevent calls to malfunctioning services. Also you should think about retry policy and client rate limit | |
| 💡 You need service discovering mechanism                                                                                                                                                                                                                |💡 Usually you need to implement Transactional outbox pattern| 


If a producer service has synchronous API to improve availability you can:
- replicate data, use copy of other services data
- handle request using only local data, send message to the broker using outbox pattern and return response. Other services eventually will update their data. This approach often is implemented using saga pattern. [[2023101222132727 Saga]]

## When you should choose asynchronous communication
- handling burst traffic or big constant write traffic(CQRS pattern)
- when consumer can be frequently unavailable, and you want to achieve fault tolerance. 
- when you want to decouple services. When producer doesn't care about who are his consumers. Instead of from service 1 directly cal endpoints to service2, ..., serviceN it is a better send an event.
- avoiding cycled dependencies. Synchronous communications like Service1 <-> Service2 can be avoided by using asynchronous communication for the opposite direction.

## References
1.  Microservices patterns by Chris Richardson, chapter 3 