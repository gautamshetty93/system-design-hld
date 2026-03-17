# Consistent Hashing

### Hashing
We have key which would be converted to hashcode through hash function

key -> hashfunction  -> hashValue
Usually we need technique called mod hashing for fixed hash tables. Based on the size of hash table it mods with the value created by hash function.
Example we have hash table of size 4. Hash function generates hashcode of 9 then 9%4=1. Value is stored in the 1st index of hash table. This works well when number of servers are *fixed*.

But in case of load balancer where number of application servers keep changing the mod hashing won't work.
In sharding also number of DBs are dynamic, in this case also mod hashing won't work.

In consistent hashing we need to rebalance by percentage on number of nodes added/removed.
Consistent hashing is a distributed system technique that maps data keys and nodes (servers) onto a logical circular ring, minimizing data remapping—typically only k/n when nodes are added or removed. By mapping both keys and servers to this ring, it solves the massive re-sharding issues of traditional modular hashing, ensuring stability, scalability, and balanced load distribution, especially when paired with "virtual nodes" to prevent data hotspots.

