
## What is Cassandra great for ?

As [datastax.com](http://www.datastax.com/dev/blog/what-cassandra-good) indicated , Cassandra shines in the situations that need : 

* fast read or write performance

* the ability to add more machines as you need additional capacity

* reliable cross-datacenter replication


Cassandra shines at online transactions(real time transactions) that have to be executed in a short time(millisecond) .

The data can be served very quickly to the user using Cassandra’s multiple caching levels , log-structured storage design, and commit log. 

Morover,Cassandra is great when data loss is unacceptable.

In addition , using MapReduce, Cassandra does very good in the  area of data management .

Now, what is MapReduce?

MapReduce is apopular algorithm by Google that allows for analytical queries to be executed on large data sets among large numbers of servers in parallel
