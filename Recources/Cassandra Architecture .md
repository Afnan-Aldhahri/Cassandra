
### Cassandra Architecture

Fisrt of all , you have to understand that Cassandra is created to deal with big data workloads

across multiple nodes with noany failure.

Cassandra handle the problem of failures by use a peer-to-peer distributed system ,

so data is distributed among all the nodes in a cluster.

Cassandra is a row-oriented database.

Cassandra's architecture empower user to connect to any node using the CQL language. 

CQL uses a similar syntax to SQL.

In CQL, database consists of tables , and a cluster has one keyspace per application. 

Developers can access CQL by cqlsh or by drivers for application languages.

Client read or write requests can be sent to any node in the cluster.

### Key structures

**Node**

This is the main infrastructure element of Cassandra.

and here data get stored  . 

**Data center**

A collection of related nodes.

The data center can be :

* a physical data center or

* virtual data center. 

each workload has its own data centers, either physical or virtual. 

It can not span physical locations.


**Cluster**

A cluster has one or more data centers.

It can span physical locations.

**Commit log**

To guarantee durability ,all data is written first to the commit log  .

So it's data can be archived, deleted, or recycled only after they flushed to SSTables.

**Table**

A collection of ordered columns fetched by row.

A row consists of columns and have a primary key. 

The first part of the key is a column name.

**SSTable**

SSTable is shortcut for sorted string table.

It is an immutable data file .

Cassandra writes memtables periodically.


### Key components for configuring Cassandra 

**Gossip**

A peer-to-peer communication protocol to share location and declare information about the other nodes in the cluster. 

**Partitioner**

A hash function that specify how to distribute the data among the nodes in the cluster .

,and its calculating the token of a partition key. 

The partition key is unique for each row of data and distributed across the cluster by the value of the token. 

**Replication factor**

The total number of replicas across the cluster. 

There is no primary replica. All replicas are equally important.
 
Replication strategy has to be greater than one.However, it should be less than the number of nodes in the cluster.

**Replica placement strategy**

To guarantee reliability , Cassandra stores copies of data on multiple nodes .

These copies called (replicas) .

A replication strategy specify which nodes to set replicas on.

The first replica of data,which is not  unique, is the first copy.

The replica placement strategy and the number of replicas  must be declared when creating a keyspace.

**Snitch**

A snitch defines groups of machines into data centers and racks .

All snitches use a dynamic snitch layer.

The role of the snitch layer is to  monitors performance and chooses the best replica for reading.

**The cassandra.yaml configuration file**

A node is configured to store its data in a directory set in the cassandra.yaml file.

Packaged installs: /var/lib/cassandra

Tarball installs: install_location/data/data




