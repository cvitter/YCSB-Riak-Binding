Riak Client for Yahoo! Cloud System Benchmark (YCSB)
--------------------------------------------------------

The Riak YCSB client is designed to work with the Yahoo! Cloud System Benchmark (YCSB) project (https://github.com/brianfrankcooper/YCSB) to support performance testing for the 2.0.X line of the Riak database. 

Implement the Riak Client
----------------------------
The following directions will help you get started with benchmarking Riak using the YCCB project and Riak client.

<ol>Download the YCSB project from https://github.com/brianfrankcooper/YCSB and extract the contents onto the machine, or machines, you plan to execute the project from. <b>Note</b>: YCSB requires Java and Maven.

<ol>Download the YCSB-Riak-Binding project and copy the Riak folder into the YCSB folder.

<ol>Modify the following sections of the YCSB's POM file to add the Riak client:

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

<ol>Perform the following operations on your Riak cluster to configure Riak for the benchmarks:

Upload the Solr search schema used to support YCSB's scan operation (<b>Note</b>: update the URL and file path to match your environment.)
```
curl -XPUT "http://localhost:8098/search/schema/ycsb" \
  -H'content-type:application/xml' \
  --data-binary @/Users/user/git/YCSB-Riak-Binding/riak/yz_schema/yscb-schema.xml
```
Create the "ycsb" bucket type and assign the ycsb search index to the bucket type.
```
riak-admin bucket-type create ycsb '{"props":{"search_index":"ycsb"}}'
riak-admin bucket-type activate ycsb
```  


<ol>Modify NODES_ARRAY in RiakDBClient.java

<ol>Build YCSB

<ol>Run a workload

