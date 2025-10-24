# Analytics: Tooling for the Data Pipeline

## Context and Problem Statement
There are many ways to load OLTP data into an analytics data store, which do we propose using? This is not an area we 
feel the need to spend a lot of money on, but we do want to avoid problems we have seen before such as stale data. 
Discussion of formalizing the source of truth for data, and even a basic dimensional model of data and how we would 
expand it over time or deal with self-service are out of scope due to time constraints.

## Considered Options

* No data pipelines; replication of OLTP data to an operational data store is enough and we get rolling with the resulting limited reporting capabilities
* Traditional ETL from OLTP + unstructured data to a star schema
* Traditional ETL from OLTP to star schema + unstructured to S3 and a mix of RedShift 
* {title of option 3}
* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: "{title of option 1}", because {justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good, because {positive consequence, e.g., improvement of one or more desired qualities, …}
* Bad, because {negative consequence, e.g., compromising one or more desired qualities, …}
* … <!-- numbers of consequences can vary -->