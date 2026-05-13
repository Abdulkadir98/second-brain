Patterns
1. Cache-aside (Lazy Loading)
2. Write through
3. Write behind

Cache-aside:
First fetch from cache. If cache-miss then go to the database. It is the most common and gives full control to the application

pros:
* Only caches data is actually accessed
* easy to implement
cons:
* data can be stale
* can cause cache stampede when hot keys expire in cache (thundering herd). To solve that use cache locks

Write-through:
Always write to both cache and database synchronously. Used for moderate write throughput and when data consistency is critical. Used to store sessions, user preferences, shopping carts etc

Pros:
* Always has the latest data
* Reads are always fast
Cons:
* Has higher write latency
* May cache data that has never been read

Write-behind (Write-back):
Write to cache first and then asynchronously write to DB. Fastest write latency. Used in higher throughput applications like analytics, logging etc where data loss is acceptable

Pros:
* Fastest write latency
* Absorbs traffic spikes

Cons:
* Risk of data loss if write to cache crashes
* Eventual consistency only

Cache eviction policies:
A cache has limited storage so need we need to get rid of keys somehow if the cache gets full

1. LRU - Least Recently Used (most popular, easy to implement and works for most cases)
2. LFU - Least Frequently Used, protects hot keys but suffers from "frequency pollution" when really popular old items never get accessed causing newer items to get evicted
3. TTL - for time sensitive and data freshness, combine with LRU/LFU for best results
4. Random eviction - works surprisingly well but not suitable for skewed workloads
5. FIFO

Cache Invalidation:
Needs to be done if the source of truth changes

1. TTL based - difficult to choose the right TTL
	1. Dilemma - smaller TTL, data is fresh but higher DB load, larger TTL load on DB is less but data is stale
2. Explicit invalidation
	1. Delete cache any time the data changes, the order matters! it is better to delete first and then write to DB to prevent race conditions
3. Pub/Sub Invalidation
4.  Stale-While-Revalidate
	1. Serve stale data immediately, refresh in the background.
5.  Cache-Aside Invalidation Pattern
	1. The most common production pattern combines cache-aside with explicit invalidation. Do not populate cache on data change, let next read do that