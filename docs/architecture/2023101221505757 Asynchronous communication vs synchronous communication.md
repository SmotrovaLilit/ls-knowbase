# Asynchronous communication vs synchronous communication

| synchronous communication | asynchronous communication |
|-------|-------|
| ⛔ Each additional service involved in processing a request decreases availability.| ✅ Don't decrease availability|
| ✅ Easiest to use|⛔ Difficult to use, some service may not support asynchronous communication|
| 💡 You must implement timeouts when executing requests, limit the count of out-standing requests, and use the Circuit Breaker design pattern to prevent calls to malfunctioning services.| |
| 💡 You need service discovering mechanism|💡 Usually you need to implement Transactional outbox pattern| 

If a producer service has synchronous API to improve availability you can:
- replicate data, use copy of other services data
- handle request using only local data, send message to the broker using outbox pattern and return response. Other services eventually will update their data. This approach often is implemented using saga pattern. [[2023101222132727 Saga]]

## References
1.  Microservices patterns by Chris Richardson, chapter 3 