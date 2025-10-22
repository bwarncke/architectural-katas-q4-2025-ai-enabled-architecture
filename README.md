# O'Reilly Architectural Katas Q4 2025: AI Enabled Architecture

## Team
**Name:** Weyland-Yutani Algorithm Recovery Squad
- [Robert Patton](https://www.linkedin.com/in/rpatton/) (FA Solutions, Lead Architect)
- [Mark Pineda](https://www.linkedin.com/in/mark-pineda-b62b98b/) (FA Solutions, Sr. Software Engineer)
- [Michael Vaughan](https://www.linkedin.com/in/michael-vaughan-5a33618/) (FA Solutions, DevOps Engineer)
- [Benjamin Warncke](https://www.linkedin.com/in/benjaminwarncke/) (Mutual of Enumclaw Insurance, Sr. Software Engineer)

[Link to this Submission Repository](https://github.com/bwarncke/architectural-katas-q4-2025-ai-enabled-architecture)

## Background
The **MobilityCorp** company provides short term rentals for last mile transport, 
offering a selection of electric scooters, bikes, cars and vans which 
are paid for by the minute. MobilityCorp has been in operation through Europe
but has not seen the usage and market growth desired, leading to an effort
to build new systems in support of that growth. A specific goal of the new
architecture is to safely use artificial intelligence to enhance the services
and address customer complaints with the existing offering. A brief outline of
the service offerings is followed by the feedback from customers.

### Key Elements of the Service Offerings
- This is a service for renting vehicles, much like other companies in the space with one slight difference in that scooters and bikes are available as well as cars. This combines what are typically services from different companies.
- There is an emphasis on enabling a better experience for the customer as well as better efficiency for MobilityCorp via systems intelligence. While this is likely true of every company, for us the company seems to be funded for and desire a complete rebuild and new approach.
- Customers are billed by the minute for any rental. All rentals have an associated timeline, for cars and vans it is the agreed upon rental period, for scooters and bikes it is a max rental period of 12 hours. 
- Rentals must be returned to designated locations. Any vehicle which is not returned to such a location by the end of the rental period or max duration are considered to be late and will incur additional fees above the per minute cost.
- Any issues with the rental vehicle will be corrected by MobilityCorp in various ways dependent on the severity.

### Customer Complaints to Address
- **C1:** Vehicles are not where they are supposed to be at pickup
- **C2:** Vehicles are dirty or need maintenance when they are picked up for use by customers
- **C3:** Vehicles are not fully charged at pickup
- **C4:** Customers are not relying on the service for regular travel

### Elements Targeted for Greater Efficiency
- **E1:** Reduce the time from vehicle return to vehicle available for rental
- **E2:** Improve inventory balancing, for example accounting for greater demand in certain areas at certain times
- **E3:** Improve occupancy rate for the fleet
- **E4:** Decrease the percentage of the fleet incurring late fees and not returning vehicles to designated locations

### Architecture Challenges
In most respects the system(s) for MobilityCorp will be like any other modern system. Browser and native mobile apps, 
OLTP and OLAP data stores, event-driven architecture where possible, cloud / infrastructure as a service etc.
There are a few areas where extra care is needed and this must be addressed in the architecture:
- **A1:** Respect customer privacy with our vehicle and usage tracking
- **A2:** Expect instability in the AI tech space
- **A3:** How will we validate the results of logic using AI?

## Overview of the Architecture
The new system, "*Hermes*", has the critical components depicted in the [diagram](#diagram-of-the-hermes-top-level-architecture) below. Where applicable we have shown
both a component name or tag as well as a technology we intend to use to support the element. Decisions which seem
like they may be debatable are covered in the following section for [Architecture Decision Records](#architecture-decision-records).

Starting in the Application Logic and Data boundary we have a browser-based UI for internal use by operations 
and administrators and native mobile apps for customers on both Android and iOS. These UIs call into the business logic 
and processes running in a monolithic application deployed on Kubernetes

### Diagram of the Hermes Top-Level Architecture
![Top-Level Architecture Diagram](diagrams/top-level-architecture.png)

## Current Challenges and Proposed Solutions

### C1: Vehicles are not where they are supposed to be at pickup
TBD

### C2: Vehicles are dirty or need maintenance when they are picked up for use by customers
TBD

### C3: Vehicles are not fully charged at pickup
TBD

### C4: Customers are not relying on the service for regular travel
TBD

## Architecture Decision Records
- [Infrastructure Hosting](adr/ADR-Cloud.md)
- [Application Architecture: Monolith or Microservices?](adr/ADR-Monolith.md)
- [AI: Which Platform or Framework to use for Building Agents?](adr/ADR-AI-Agent.md)
- [Analytics: Tooling for the Data Pipeline](adr/ADR-Data-Pipeline.md)

## Assumptions
- Tesla
- Purpose-built scooters and bicycles
- GPS connectivity
- At-worst intermittent cellular connectivity

## AI Enablement
- Pricing Algorithm
- Predictive inventory usage
- Return and damage analysis

## Parking Lot / Ideas for the Future
Some ideas we discussed were discarded for now because of time constraints or 
outside forces such as regulations. This section very briefly covers those ideas so they are
not lost as the company grows and the legal and regulatory environment changes.

- Use of autonomous vehicles for inventory management
- Loss prevention
- Criminal usage detection