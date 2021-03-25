# Reactive-Microservice-Principles
--------------------------------

## Reactive Manifesto
------------------
### Responsive 
- Responsive systems provide timely responses against customer interation
- Responsive systems operate with consistency and consequently enhance visibility into anomalies
- First byte latency as an indication of customer experiencee
- Server and client side metrics
	
### Resilience | the capactity to recover quickly from difficulties, stay responsiveee under failure


#### Scope
It is important to understand the scope of what it means for a system to resist adversity:

- What critical capabilities/services must the system continue to provide despite disruptions?
- What types of adversities can disrupt the delivery of these critical capabilities (i.e., what adverse events and conditions must the system be able to tolerate)?
- What are the types and levels of harm to what assets that can cause these disruptions?

#### Objective
A system is resilient to the degree to which it rapidly and effectively protects its critical capabilities from disruption caused by adverse events and conditions.

The four functions of protection:

- **Resistance**
	- Ability to passively prevent or minimize harm from adverse event or condition. 
	- 	Resilience techniques include a modular architecture that prevents failure propagation between modules, a lack of single points of failure.
	-
- **Detection** 
	- Ability to actively detect (via detection techniques):
		- Loss or degradation of critical capabilities
		- Adverse events and conditions that can harm critical capabilities or related assets

- **Reaction** 
	- Ability to actively react to the occurrence of an ongoing adverse event or respond to the existence of an adverse condition (whereby the reaction is implemented by reaction techniques). 
	- Reaction techniques include employing exception handling, degraded modes of operation, and redundancy with voting and

- **Recovery** 
	- Ability to actively recover after the adverse event is over (whereby recovery is implemented by recovery techniques). 
	- Recovery can also be partial or minimal (e.g., degraded mode operations providing only limited services). 
	- Recovery might also include the system evolving or adapting (e.g., via reconfiguring itself) to avoid future occurrences of the adverse events or conditions.


### Achieved by 
- Replication: 
	- Distribute workload evenly across multiple servers
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


# SAGA: Disgining a State Machine
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



# Management endpoints
https://channel9.msdn.com/Shows/On-NET/NET-Microservices-with-Steeltoe

### /health
Returns UP or DOWN information based on built-in health contributors, or any custom ones you write.
https://dzone.com/articles/an-overview-of-health-check-patterns

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

