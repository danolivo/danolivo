## Hi, I'm Andrey 👋

I'm a PostgreSQL Internals Engineer based in Madrid, passionate about data management technologies — query planning and executing, distributed transactions and scalability.

## Recent Projects

### Core features

* __Enforce sorted scan__. The core feature suggests that when an SQL query includes an ORDER BY clause for a relation and a LIMIT clause, it is beneficial to have a sorted scan path among the possible scan operators during query optimisation. For instance, this could involve pushing the sort operation to the outer side of an OUTER JOIN. Branches: [master](https://github.com/danolivo/pgdev/tree/enforce-presorted-scan-on-query-pathkeys), [PG 18](https://github.com/danolivo/pgdev/tree/enforce-presorted-scan-on-query-pathkeys-pg18), [alternative-master](https://github.com/danolivo/pgdev/tree/bounded-left-join-outer), [alternative PG 18](https://github.com/danolivo/pgdev/tree/bounded-left-join-outer-v18); [notes](https://www.notion.so/Push-Sort-into-the-outer-of-OUTER-JOIN-329ca5f34df28038904fd0afbbe4daf8), [discussion](https://www.postgresql.org/message-id/flat/19a9265c-c441-4a43-bc0d-dac533438da0%40gmail.com).
* __[Selectivity models](https://github.com/danolivo/pgdev/tree/selectivity-correlation-models)__. The core feature enables users to choose how to combine selectivity estimations on independent clauses. Essential feature in case when the query contains multi-filter or multi-join clause restrictions.
* [Referenced generic plan](https://www.postgresql.org/message-id/19919494-92a8-4905-a250-6cf17b89f7c3@gmail.com).

### Extensions

* __[pg_track_optimizer](https://github.com/danolivo/pg_track_optimizer)__. An extension which is designed to reveal how _effectively_ the database instance executes queries. Provides multiple dimensionless metrics wrapped into a _statistics_ custom type to expose fluctuations of each parameter.
* __[pg_pathcheck](https://github.com/danolivo/pg_pathcheck)__. An extension that enables users of Postgres or PG fork to check (since PG19) potential vulnerabilities of the planner code.
* [safesession](https://github.com/danolivo/safesession). An extension that allows connection poolers and automation tools to change a connection to read-only mode, preventing any reversal through role changes or escalation of privileges. Inspired by the popularity of MCP servers and the necessity to give an AI agent database access.
* [lolor](https://github.com/pgEdge/lolor). Contributor, not an original author. Dedicated to flexible management of large objects - moving out of the system catalogue, logically replicated, etc. 

### Experiments
* [Batch insert](https://github.com/danolivo/pgdev/tree/lr-multi-insert) in logical replication. An attempt to employ the COPY multi-insert approach to quickly replicate massive batches of tuples. [specs](https://github.com/danolivo/pgdev/wiki/Technical-Specification:-Batched-Multi%E2%80%90Insert-for-PostgreSQL-Logical-Replication), [Design](https://github.com/danolivo/pgdev/wiki/Batched-Multi%E2%80%90Insert-for-Logical-Replication-Apply-—-Design-Explanation).
