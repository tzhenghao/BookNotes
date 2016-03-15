Distributed Systems
-------------------

Basic requirements - nodes should be autonomous so that they can work independently.

Any node needs to have a communication link directly/indirectly to another node.

Advantages:
1. Resource sharing

Replication of resources - provide fault tolerance.

Distibuted systems modeled as a graph.

Some nodes not connected with each other - rely on neighboring nodes for connection.

Grid consists of loosely couple, heterogenous and geographically dispersed computing
elements.

Grid computing provides parallelization.

grids require general software libraaries called middleware.

Resource discovery
Resource allocation -  map resources to application requirements for the best performance.

In grids, nodes may abort due to faults

Mobile Ad Hoc Networks - each node functions as a router. disaster relief operations
military networks and vehicular ad hoc networks.

Wireless sensor Networks
-----------------------
Multi-hop communication

Basic Models
-----------
1. Message passing
2. Shared-memory Models

Messages are communicated in rounds in synchoronous messsage passing. messages
sent in round k has to be delivered before message k + 1. Async assumes that they will
eventually reach their respective destinations.

Distributed shared-memory systems implement shared memory model over the message passing Models

Protocol stack is responsible for the correct and timely delivery of messages between the
nodes of the distributed system.

Distributed systems do not have a comon clock - require synchronization at the hardware.

Message passing between the nodes.

Design issues
-------------
1. Leader election
2. Fault tolerance
3. Load balancing

Symmetric distributed algorithm - executed on all nodes of the distributed system.
Asymmetric - may be running different components of an asymmetric distributed algorithm.

Load balancing
-------------
Response time, throughput

Hard real-time task
Soft real-time task

Fault tolerance
---------------
Consensus Algorithms - another area of research in fault tolerant computing.
Check-pointing and recovery procedures record the state of the software periodicallyon a secondary storage

In case of faults, the system may be started from last recorded state.

Self-stabilizing algorithms

Distributed Graph algorithms
---------------------------
Using heuristics + approximation algorithms to find suboptimal solutions to the problems
are the only choices in these situations.


