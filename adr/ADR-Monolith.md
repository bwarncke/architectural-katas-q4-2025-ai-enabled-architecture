# Application Architecture: Monolith or Microservices?

## Context and Problem Statement
Should the application architecture be monolithic or microservice-based?

## Considered Options

* Monolith
* Microservices

## Decision Outcome

Chosen option: "Monolith", because we do not think enough has been learned about the business domain from the legacy 
to usefully break it down into microservices. At the same time, our focus is on dramatic improvements to process and logic
in the area of AI and we do not want to convert to microservices while such changes are ongoing. 

### Consequences

* Good, because we limit the scope of change in the architecture in a significant way
* Bad, because we do not generally gain the benefits of serverless/as needed technology at the app tier, such as Lambda. 
* Even Trade: we gain the headaches of dealing with Kubernetes while avoiding the headaches of dealing with Lambda.
