# Reactive-Microservice-Principles
--------------------------------

## Reactive Manifesto
------------------
### Responsive 
- Responsive systems provide timely responses against customeer interation
- Responsive systems operate with consistency and consequently enhance visibility into anomalies
- First byte latency as an indication of customer experiencee
- Server and client side metrics
	
### Resilience | the capactity to recover quickly from difficulties, stay responsiveee under failure
- Achieved by 
	- Replication: 
		- Distribute workload evenly across multiple serveers
			- Single failure is isolated against other servers
			- Ex. AWS Auto scaling 
		- Containment & Isolation
			- Decoupling the architecture
			- Ex: https
		. Delegation
			- Passing responsibility passes from one component to another
			- Enable focus on core capability
			- Circuit Breaker
			- Bulkhead	

### Elastic | Elasticly is not scalability

Elasticity is generally achieved by sharding, replication and workload distribution
Example: Bittorrent - distributed hash table used, distibuted conetent between peers, Ex. Distributed hash table concepts implemented by AWS S3



### Message Driven |  protocol driven application components
- Accepted status is aynchronous by design
- Callback mechanisms eliminate resource wait
- Ex: webhooks


- Choreographed SAGAs
	- Centered on events going into global event store
	- Publishers
	- Consumers

- Orchestrated SAGAs.
	- Centered on commands rather events
	- Publish
	- Consume


SAGA: Disgining a State Machine
--------------------------
A Saga is basically a sequence of local transactions. For every transaction performed within a Saga, the service performing the transaction publishes an event. The subsequent transaction is triggered based on the output of the previous transaction. And if one of the transactions in this chain fails, the Saga executes a series of compensating transactions to undo the impact of all the previous transactions.


----------------------------------

> Event Sourcing
> Idempotency
> Commutative Messaging
> Distributed Transactions


...
Hexagonal Architecture 
Layered Architecture
Monoliths > (Single Unit, Complications of continous deliveery and casceding failures)
Microservices > (Modular component, isolated database, )



## Management endpoints
https://channel9.msdn.com/Shows/On-NET/NET-Microservices-with-Steeltoe

### /health
Returns UP or DOWN information based on built-in health contributors, or any custom ones you write.

### /info
Returns Git information as well as any app configuration values under the “info” key.

### /loggers
Lets you view and change the log level for your .NET applications.

### /trace
Returns the last handful of requests to your app, with metadata about the requestor.

### /refresh
Triggers a reload of configuration values from configuration sources.

### /env
Returns configuration values and keys that your app is using.

### /mappings
Returns all the routes exposed by the application.

### /metrics
Returns a wide range of CLR, HTTP client, and HTTP server metrics for your app.

### /dump
Returns information about all the threads used by your application.

### /heapdump
Generates a mini-dump of your application for later analysis.

### /cloudfoundry
Enables integration with the Pivotal Applications Manager 

