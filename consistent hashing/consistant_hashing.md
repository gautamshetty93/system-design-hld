# Consistent Hashing

### Hashing
We have key which would be converted to hashcode through hash function

key -> hashfunction  -> hashValue
Usually we need technique called mod hashing for fixed hash tables. Based on the size of hash table it mods with the value created by hash function.
Example we have hash table of size 4. Hash function generates hashcode of 9 then 9%4=1. Value is stored in the 1st index of hash table.

But in case of load balancer where number of servers keep changing the mod hashing won't work.
In sharding also number of DBs are dynamic, in this case also mod hashing won't work.
