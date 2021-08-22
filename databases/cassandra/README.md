
# Why Cassandra?

1 - Scalable

2 - Distributed

3 - HighPerformance

4 - Opensource

5 - fault-tolerant

## Architecture
### Partitioning
Uses a consistent hashing algorithm ( use the key of key-value concept to assign rows to partitions ). It also uses tokens& rings partitioning algorithm, which means after writing some data the node1(with token1) will walk through the ring clockwise and writes on other nodes in the ring. So there is no random replication. 
You can change base topology by assigning multiple tokens to nodes.
In many-to-one token mapping ( e.x: n1:T1, T2, T3 ), the node is an actual node, and evert partitions are VNodes( virtual nodes in the ring).
### Replication:
<b>Network Awareness:</b>
make your data highly available.
It helps you make policies about how data and nodes should partition your data in different regions, data centers, and server rags.
2.1.1: Network topology strategy

2.1.2: Simple strategy

###  Data versioning: 
Cassandra uses timeStamp to manage concurrent data. Which will follow the Last-write-wins algorithm. so f some concurrent update is happening and someone  
###  Consistency: 
One =  it will respond write operation completed if data is written, at least one replica.

Two ....

Three ...

Quarium ...

All ...

Local Quaram = Only respond write operation is completed when the majority of the datacenter is written.

Each Quaram ...


### Failover detection:
 uses <b>GOSSIP</b> protocol, which uses the heartbeat of each node to recognize failure.
### cassandra storages :

1.commit logs: ( to make consitency and its temprary storage)

2.memTables (memory storage)

3.ssTables (phisical storage )

### CQL

KeySpace == database &&
Table==Table


<i>Batch </i>

run group multiple queries as a single query.
Materialized views => it's like creating views. 

#### <i>functions:</i>
Scalar functions :(specific to oen row)  Cast , Current_date , ......

Aggegate functions :(multiple rows) Min ,Max,Sum ,....

UDF (user-defined functions)

#### <i>JSON SUPPORT: </i>
Seamless support (one col)
Triggers:

#### <i>DATA Modeling:</i>
these are two types of keys, and you should make queries first before creating tables.
There are two types of keys :
Primary and Composite(clustering key which uses to sorting data within a partition)

#### <i>Cassandra operations:</i>
Snitch => network topology ( you can set it Dynamical snitching o reduce latency )
Bootstrap => nodes management in Cassandra cluster
Repair => Full repair, Subrange, and increment repairs
ReadRepair
Compression => ssTable compression( like snappy , lazy and ...)
BackUps and Bulk loading
Metrics( like Prometheus)

#### <i>Tools:</i>

CQLSH => run sql queries 

SSTABLEtool => bulk load dump metadate repair

Cassandra stress=> stress testing Cassandra cluster 
