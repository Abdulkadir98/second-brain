Data structure that saves key-value pairs and offers constant time look-ups.
Supports three basic operations in constant time O(1) -
1. Insert
2. ContainsKey
3. Delete


Does not provide ordering of elements, tree or heap based data structure must be used if ordering is needed.

### Hash function:
 A mathematical function that maps a key from a universe (Set) of keys to an index in the underlying hash table array.
 
 ### Quick and dirty hash functions
 Modulo and compression - It is common to convert the key to be hashed to a really long number (This step can be skipped if the key is already numeric) and use the modulo operation to reduce the number to within the number of buckets in the hash table. The idea is that the hash function should be able to spread the data as uniformly as possible
 
 #### Some Rules-of-thumbs
 * Choose the size of the hash table (n) to be a prime number, so it doesn't share too many factors with the modulo of the size of the hash table
 * Size n should not be too close to the power of 2 (If memory location is used as a hashcode)
 * Size n should not be too close to power of 10 (Example 10 digit phone numbers)
 
 ### Collision resolution:
 A collision occurs when two keys resolve to the same index position in the hash table
 
 ### 3 strategies to resolve collision-
 1. Chaining - List of linked lists where each index in the array stores a pointer to the head of a linked list. If two keys collide, then traverse the list in that bucket and add the key at the end of that list
 2. Linear Probing - Each bucket (index position) saves only one object, if resolved to the same bucket then advance to the next position, and the next, and so on
 3. Double Hashing - The first hash functions finds the bucket to insert in, if it's occupied then use the second hash function as an offset to the first index


#### Notes
* Deletion in Linear chaining is easy but it's not very memory efficient
* Deletion is tricky in linear probing but it's memory efficient




#### References
https://algs4.cs.princeton.edu/34hash/
https://www.youtube.com/watch?v=2MocX5A3pSs&list=PLXFMmlk03Dt7Q0xr1PIAriY5623cKiH7V&index=69&ab_channel=StanfordAlgorithms