The 'I' in ACID Transactions (Atomicity, Consistency, Isolation, and Durability)

There are 4 isolation levels. In the order that provides most isolation to least in transactions
- Serializable
- Repeatable Read
- Read Committed
- Read Uncommitted

Anomalies that occur when Isolation is absent:
- Lost Updates
- Dirty Reads
- Fuzzy/Non-repeatable reads

Reference: https://dev.mysql.com/doc/refman/5.7/en/innodb-transaction-isolation-levels.html