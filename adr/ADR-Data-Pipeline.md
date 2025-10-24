# Analytics: Tooling for the Data Pipeline

## Context and Problem Statement
There are many ways to load OLTP data into an analytics data store, which do we propose using? This is not an area we 
feel the need to spend a lot of money on, but we do want to avoid problems we have seen before such as stale data. 
Discussion of formalizing the source of truth for data, and even a basic dimensional model of data and how we would 
expand it over time or deal with self-service are out of scope due to time constraints.

## Considered Options

* No data pipelines; replication of OLTP data to an operational data store is enough and we get rolling with the resulting limited reporting capabilities
* Traditional ETL from OLTP + unstructured data to a star schema
* Traditional ETL from OLTP to star schema + unstructured to S3 with RedShift providing data lakehouse functionality over it
* OLTP data to star schema via Data Firehose, S3 and Glue (or similar)

## Decision Outcome

Chosen option: "OLTP data to star schema via Data Firehose, S3 and Glue (or similar)", because 
it provides near real-time data and meets expected initial needs while allowing for sophistication to
be added later without significant rework. For example, we can start with this then later to the architecture
to support ingestion of unstructured data without having to redo what we built for the structured data.

### Consequences

* Good, because it provides nearly up to data information to downstream consumers
* Good, because it can be matured
* Bad, because it relies on nearly every developer to send data out to EventBridge to be fed into Data Firehose, this can be easily forgotten or not maintained (though that causes other critical problems for the event driven elements of the architecture)