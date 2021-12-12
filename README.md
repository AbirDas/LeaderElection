# LeaderElection

This is a simple implementation of the ZooKeeper leader election algorithm as outlined here
https://zookeeper.apache.org/doc/r3.7.0/

Code guide and algorithm of zookeeper executor referred from here
https://zookeeper.apache.org/doc/r3.7.0/javaExample.html

ZookeeperElectableClient.java
- An abstract ZooKeeper client that implements the leader election algorithm.
- The method performRole() must be implemented in a child class.  This function is intended to
contain the work that the client node must actually perform (conditioned on whether or not it
is the leader).

Executor.java
The Executor object is the primary container of the sample application. It contains both the ZooKeeper object, DataMonitor.
As discribe, Conventionally, ZooKeeper applications are broken into two units, one which maintains the connection, and the other which monitors data. In this application, the class called the Executor maintains the ZooKeeper connection, and the class called the DataMonitor monitors the data in the ZooKeeper tree. Also, Executor contains the main thread and contains the execution logic. It is responsible for what little user interaction there is, as well as interaction with the executable program you pass in as an argument and which the sample (per the requirements) shuts down and restarts, according to the state of the znode.
