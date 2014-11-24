Riak Client for Yahoo! Cloud System Benchmark (YCSB)
--------------------------------------------------------

The Riak YCSB client is designed to work with the Yahoo! Cloud System Benchmark (YCSB) project (https://github.com/brianfrankcooper/YCSB) to support performance testing for the 2.0.X line of the Riak database. 

Implement the Riak Client
----------------------------
The following directions will help you get started with benchmarking Riak using the YCCB porject and Riak client.

1. Download the YCSB project from https://github.com/brianfrankcooper/YCSB and extract the contents onto the machine, or machines, you plan to execute the project from. <b>Note</b>: YCSB requires Java and Maven.

2. Download the YCSB-Riak-Binding project and copy the Riak folder into the YCSB folder.

3. Modify the following sections of the YCSB's POM file to add the Riak client:

```
<properties>
  ...
  <riak.version>2.0.2</riak.version>
  ...
</properties>
```

```
<modules>
  ...
  <module>riak</module>
  ...
</modules>
```


4. Modify NODES_ARRAY in RiakDBClient.java

5. Build YCSB

6. Run a workload



Implement the Scan Operation
------------------------------

1. Upload the Solr Schema


