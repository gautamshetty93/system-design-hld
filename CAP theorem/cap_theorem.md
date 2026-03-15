# CAP Therorem
This talks about desirable property of distributed system. CAP stands for <ins>Consistency, Availability and Partition tolerance.</ins>

Consistency -> Data read should be always same when it read from any node
Availability -> All node should be always responding
Partition tolerance -> Even when some node is down, we should be able to get response for user request.

But all three at a time is not possible.
Possible:
1. CA -> When nodes should be always available and consistant then partition tolerance is not available. 
2. CP -> When there is some breakage in connection, at that time consistency is not possible because updating doesn't happens
3. AP -> When there is some breakage in connection, we can not check all the nodes status. Some would be unavailable because of partition tolerance