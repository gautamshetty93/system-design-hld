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