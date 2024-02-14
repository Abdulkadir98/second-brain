What is a thread-safe class?
 - A class is thread-safe if it behaves correctly when one or more than one thread accesses it, with timing or interleaving of operations causing no impact on the correctness of the class and with no coordination among the threads


**Intrinsic Locks**
Each Java object can act as a lock for synchronization purposes. A synchronization block in Java acts as a mutex (mutual exclusion) where only one thread is able to own the lock.
A synchronized block has two components - The reference to an object which acts as a lock and the code block which the lock guards. The *synchronized* method is shorthand for a synchronized block whose the lock is the object of the method and the code block spans the entire method body.

Intrinsic locks in Java are **reentrant** which means that a thread is able to acquire a lock if it already holds it. Each lock has a thread owner associated with it and a counter gets incremented each time the lock gets acquired. After the count reaches 0 the lock is released. The "locking" in Java is on a per-thread basis which is different from PThreads (POSIX threads) which are on per invocation basis.

Locking/synchronization provides more than mutual exclusion -  it also provides memory visibility. So threads accessing shared mutable variables must must use synchronization on the same lock.

**volatile** variables: A variable is a good candidate to be declared volatile if it does not participate in invariants involving othet state variables