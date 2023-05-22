In the first days, applications were built monolithically which means all the logic was in one place and the app was a single unit. Extending applications and increasing their complexity made them difficult to maintain so a solution was to build applications in multitier architecture (like MVP) which contained three layers, each having their tasks. After a while the same problem showed up again so the new approach was to use a new architecture called microservice. 
In this architecture, each service is being developed, built, tested separately with their own database and even maybe different languages and deployed on different infrastructures. 
Microservice architecture contains some important components:


#### Monitoring Tools


#### Container Tools


#### Container Orchestration Tools
Docker Swarm - Kubernetes


#### CI/CD Pipelines


#### Brokers
Communications between microservices is conducted by tools like [message brokers]([[What are message brokers]]). 


#### Load Balancer


#### Reverse Proxy


#### API Gateway
