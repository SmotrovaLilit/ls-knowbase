# Stateful vs Stateless servers

## Stateful
- ⛔ Every request from the same client must be routed to the same server. This can be done with sticky sessions in most load balancers; however, this adds the overhead. Adding or removing servers is much more difficult with this approach. It is also challenging to handle server failures.

## Stateless
- ✅ A stateless system is simpler, more robust, and scalable. 
- ✅ Autoscaling means adding or removing web servers automatically based on the traffic load. After the state data is removed out of web servers, auto-scaling of the web tier is easily achieved by adding or removing servers based on traffic load.

## Session data
Could be a relational database, Memcached/Redis, NoSQL, etc. The NoSQL data store is chosen as it is easy to scale.