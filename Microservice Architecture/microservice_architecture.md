# Microservices architecture and Patterns

Different types of system architectures :
1. Monolithic -> Legacy systems where everything happens in a single system
Disadvantage of this is overloading of IDE, scaling is hard, CI job fails and entire system will be down.
Tight coupling and small changes requires testing of entire system.
2. Microservices -> Whole system is divided into multiple small. All the disadvantages of monoliths are addressed here.
Disadvantage of this are: you need to divide the monoliths properly, else there will be more need of communication and latency increase.
Transaction management will be difficult, because of multiple DBs. 

Different stages of microservices :
1. Decomposition -> Decompose the big monolith to different microservices based on the business capability
2. Databases -> Approach -> Database per service/shared database
3. Communication -> via API, via Events
4. Integration -> Microservice also should get integrated with user interface using API gateways.
5. Deployment 
6. Observability -> Monitoring

These are all the different patterns for microservices.

## Decomposition Pattern
This pattern depends on how services are defined into multiple micro services based on the business requirement. Each part of business is made as a new service.

## STRANGLER Pattern
We have a controller and old legacy system. Old API traffic comes to controller, then we create few service to created different service, which is newly created microservices. Similarly we redirect the small services and redirect the traffic as times goes on. 
We slowly reduce traffic to the legacy system and increase traffic to new microservice. This is kind of slowly strangling the monolith and moving to microservice.

## Data Management in Microservice
1. Database for each individual service->Each microservice has its own DB.
2. Shared database->Different services has single database. It is easier to join for different services, also it is easy to maintain transactions.
But drawback in this is :
 - we would not be able to scale for an individual service
 - Columns would not be able to delete shared cells, it needs to think of other services also.

## SAGA Design pattern
When each service have its own DB, then it is very difficult to handle transactions. When some transaction fails then its hard to roll back commits in other DBs. SAGA pattern comes into picture to resolve this.
SAGA uses events to co-ordinate between different services and its DBs.
It uses 2 different approaches to solve this :
1. Choreography -> Each service send their operation to choreographer queue(like an event queue) and other services listens to it and proceeds with their operation.
2. Orchestrator -> It performs operation by giving turn to each service and if it fails then goes back to previous services to rollback.

## CQRS (Command Query Request Segregation)
Design pattern separates the operations for reading data from those for writing data into distinct models
Commands: These are operations that change the state of the application (Create, Update, Delete). Commands are task-based, focus on business logic and validation, and do not return data.
Queries: These are operations that read the state of the application. Queries return data transfer objects (DTOs) and can use simple models to avoid complex mapping and improve speed.