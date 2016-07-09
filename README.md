# Cassandra

Cassandra is designed to handle big data workloads across multiple nodes with no single point of failure.
Its architecture is based on the understanding that system and hardware failures can and do occur.
Cassandra addresses the problem of failures by employing a peer-to-peer distributed system across
homogeneous nodes where data is distributed among all nodes in the cluster. Each node frequently
exchanges state information about itself and other nodes across the cluster using peer-to-peer gossip
communication protocol. A sequentially written commit log on each node captures write activity to ensure
data durability. Data is then indexed and written to an in-memory structure, called a memtable, which
resembles a write-back cache. Each time the memory structure is full, the data is written to disk in an
SSTables data file. All writes are automatically partitioned and replicated throughout the cluster. Cassandra
periodically consolidates SSTables using a process called compaction, discarding obsolete data marked
for deletion with a tombstone. To ensure all data across the cluster stays consistent, various repair
mechanisms are employed.
