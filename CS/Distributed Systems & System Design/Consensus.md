Consensus problem:
A problem in distributed computing that requires a number of processes to agree on a single data value.

Applications where consensus is required:
* Leader election - which node has the primary database
* Distributed locks - only one process must hold the lock, all nodes must agree
* Atomic commits - either every succeeds or fails, no partial transactions
* State machine replication - All machines process the same commands in the same order

Byzantine General's problem
Byzatine faults - when a process behaves in a malicious or arbitrary way

Consensus protocols must satisfy these properties:
* Agreement - All non-faulty nodes must agree on the same value
* Validity - the value must have been proposed by some node
* Termination - All non-faulty nodes eventually decide (liveness)
* Integrity - A node decides at most once