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
