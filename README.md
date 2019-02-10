# Data Migrations with Spring Batch

Criteria:

- many gigabytes of data migrated for modernized version of service
- parallizeable
  - no direct communication (calls) between the E/T/L steps (I.E. message-based where steps would consume topics and produce new ones picked up by next step)
- progress tracking and summary statistics
  - errors handled, records not moved recorded
- resumeable

Questions:

- what's the best wat to ETL from an old to new schema(a), i.e. from a legacy monolith to a set of services?

## Options:

- Spring Batch
- Spark
- Message-based, i.e. Kafka

### In Approach:

- Instead of sending GBs of data in large batches, stream the data to the required service using reactive