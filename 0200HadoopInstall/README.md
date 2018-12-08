[Contribution guidelines for this project](READMETEST/README.md)

### 1. Prerequisites
  - Git
  - Docker
    

### 2.  From the terminal window pull sequenceiq/hadoop-docker. 

```bash
    $ docker pull sequenceiq/hadoop-docker:2.7.0

```

This takes a long time to download.  The output will look like this:


````
               ......

    60a65f8179cf: Pull complete
    046b321f8081: Pull complete
    Digest: sha256:a40761746eca036fee6aafdf9fdbd6878ac3dd9a7cd83c0f3f5d8a0e6350c76a
    Status: Downloaded newer image for sequenceiq/hadoop-docker:2.7.0

````

### 3.  Run Hadoop 

```bash
    $ docker run -it sequenceiq/hadoop-docker:2.7.0 /etc/bootstrap.sh -bash

```

You are now talking to the HDFS machine

````
    Starting sshd: [60G[[0;32m  OK  [0;39m]
 
     Starting namenodes on [41f20c6992c9]
     41f20c6992c9: starting namenode, logging to /usr/local/hadoop/logs/hadoop-root-namenode-41f20c6992c9.out
     localhost: starting datanode, logging to /usr/local/hadoop/logs/hadoop-root-datanode-41f20c6992c9.out
     Starting secondary namenodes [0.0.0.0]
     0.0.0.0: starting secondarynamenode, logging to /usr/local/hadoop/logs/hadoop-root-secondarynamenode-41f20c6992c9.out
     starting yarn daemons
     starting resourcemanager, logging to /usr/local/hadoop/logs/yarn--resourcemanager-41f20c6992c9.out
     localhost: starting nodemanager, logging to /usr/local/hadoop/logs/yarn-root-nodemanager-41f20c6992c9.out
     [?1034hbash-4.1# 

````

### 3.  Run MapReduce

```bash
   cd $HADOOP_PREFIX
   # run the mapreduce
   bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.0.jar grep input output 'dfs[a-z.]+'
   
   # check the output
   bin/hdfs dfs -cat output/*

```

Output:

````
bash-4.1# bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.0.jar grep input output 'dfs[a-z.]+'
18/12/08 16:38:53 INFO client.RMProxy: Connecting to ResourceManager at /0.0.0.0:8032
18/12/08 16:38:55 INFO input.FileInputFormat: Total input paths to process : 31
18/12/08 16:38:55 INFO mapreduce.JobSubmitter: number of splits:31
18/12/08 16:38:55 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1544304696146_0001
18/12/08 16:38:56 INFO impl.YarnClientImpl: Submitted application application_1544304696146_0001
18/12/08 16:38:56 INFO mapreduce.Job: The url to track the job: http://234c9c01d7c6:8088/proxy/application_1544304696146_0001/
18/12/08 16:38:56 INFO mapreduce.Job: Running job: job_1544304696146_0001
18/12/08 16:39:07 INFO mapreduce.Job: Job job_1544304696146_0001 running in uber mode : false
18/12/08 16:39:07 INFO mapreduce.Job:  map 0% reduce 0%
18/12/08 16:39:39 INFO mapreduce.Job:  map 19% reduce 0%
18/12/08 16:40:15 INFO mapreduce.Job:  map 35% reduce 0%
18/12/08 16:40:19 INFO mapreduce.Job:  map 35% reduce 12%
18/12/08 16:40:33 INFO mapreduce.Job:  map 48% reduce 12%
18/12/08 16:40:34 INFO mapreduce.Job:  map 52% reduce 12%
18/12/08 16:40:37 INFO mapreduce.Job:  map 52% reduce 17%
18/12/08 16:40:48 INFO mapreduce.Job:  map 55% reduce 17%
18/12/08 16:40:50 INFO mapreduce.Job:  map 58% reduce 17%
18/12/08 16:40:51 INFO mapreduce.Job:  map 61% reduce 17%
18/12/08 16:40:52 INFO mapreduce.Job:  map 68% reduce 17%
18/12/08 16:40:53 INFO mapreduce.Job:  map 68% reduce 20%
18/12/08 16:40:55 INFO mapreduce.Job:  map 68% reduce 23%
18/12/08 16:41:07 INFO mapreduce.Job:  map 71% reduce 23%
18/12/08 16:41:08 INFO mapreduce.Job:  map 77% reduce 23%
18/12/08 16:41:09 INFO mapreduce.Job:  map 81% reduce 23%
18/12/08 16:41:10 INFO mapreduce.Job:  map 84% reduce 27%
18/12/08 16:41:13 INFO mapreduce.Job:  map 84% reduce 28%
18/12/08 16:41:26 INFO mapreduce.Job:  map 87% reduce 28%
18/12/08 16:41:27 INFO mapreduce.Job:  map 90% reduce 28%
18/12/08 16:41:28 INFO mapreduce.Job:  map 97% reduce 30%
18/12/08 16:41:29 INFO mapreduce.Job:  map 100% reduce 30%
18/12/08 16:41:30 INFO mapreduce.Job:  map 100% reduce 100%
18/12/08 16:41:31 INFO mapreduce.Job: Job job_1544304696146_0001 completed successfully
18/12/08 16:41:32 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=345
		FILE: Number of bytes written=3697476
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=80529
		HDFS: Number of bytes written=437
		HDFS: Number of read operations=96
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=2
	Job Counters 
		Launched map tasks=31
		Launched reduce tasks=1
		Data-local map tasks=31
		Total time spent by all maps in occupied slots (ms)=669999
		Total time spent by all reduces in occupied slots (ms)=107329
		Total time spent by all map tasks (ms)=669999
		Total time spent by all reduce tasks (ms)=107329
		Total vcore-seconds taken by all map tasks=669999
		Total vcore-seconds taken by all reduce tasks=107329
		Total megabyte-seconds taken by all map tasks=686078976
		Total megabyte-seconds taken by all reduce tasks=109904896
	Map-Reduce Framework
		Map input records=2060
		Map output records=24
		Map output bytes=590
		Map output materialized bytes=525
		Input split bytes=3812
		Combine input records=24
		Combine output records=13
		Reduce input groups=11
		Reduce shuffle bytes=525
		Reduce input records=13
		Reduce output records=11
		Spilled Records=26
		Shuffled Maps =31
		Failed Shuffles=0
		Merged Map outputs=31
		GC time elapsed (ms)=2209
		CPU time spent (ms)=20850
		Physical memory (bytes) snapshot=6898974720
		Virtual memory (bytes) snapshot=23284989952
		Total committed heap usage (bytes)=4606918656
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=76717
	File Output Format Counters 
		Bytes Written=437
18/12/08 16:41:32 INFO client.RMProxy: Connecting to ResourceManager at /0.0.0.0:8032
18/12/08 16:41:32 INFO input.FileInputFormat: Total input paths to process : 1
18/12/08 16:41:32 INFO mapreduce.JobSubmitter: number of splits:1
18/12/08 16:41:33 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1544304696146_0002
18/12/08 16:41:33 INFO impl.YarnClientImpl: Submitted application application_1544304696146_0002
18/12/08 16:41:33 INFO mapreduce.Job: The url to track the job: http://234c9c01d7c6:8088/proxy/application_1544304696146_0002/
18/12/08 16:41:33 INFO mapreduce.Job: Running job: job_1544304696146_0002
18/12/08 16:41:46 INFO mapreduce.Job: Job job_1544304696146_0002 running in uber mode : false
18/12/08 16:41:46 INFO mapreduce.Job:  map 0% reduce 0%
18/12/08 16:41:56 INFO mapreduce.Job:  map 100% reduce 0%
18/12/08 16:42:07 INFO mapreduce.Job:  map 100% reduce 100%
18/12/08 16:42:07 INFO mapreduce.Job: Job job_1544304696146_0002 completed successfully
18/12/08 16:42:07 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=291
		FILE: Number of bytes written=230541
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=569
		HDFS: Number of bytes written=197
		HDFS: Number of read operations=7
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=2
	Job Counters 
		Launched map tasks=1
		Launched reduce tasks=1
		Data-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=7654
		Total time spent by all reduces in occupied slots (ms)=8735
		Total time spent by all map tasks (ms)=7654
		Total time spent by all reduce tasks (ms)=8735
		Total vcore-seconds taken by all map tasks=7654
		Total vcore-seconds taken by all reduce tasks=8735
		Total megabyte-seconds taken by all map tasks=7837696
		Total megabyte-seconds taken by all reduce tasks=8944640
	Map-Reduce Framework
		Map input records=11
		Map output records=11
		Map output bytes=263
		Map output materialized bytes=291
		Input split bytes=132
		Combine input records=0
		Combine output records=0
		Reduce input groups=5
		Reduce shuffle bytes=291
		Reduce input records=11
		Reduce output records=11
		Spilled Records=22
		Shuffled Maps =1
		Failed Shuffles=0
		Merged Map outputs=1
		GC time elapsed (ms)=100
		CPU time spent (ms)=2710
		Physical memory (bytes) snapshot=389574656
		Virtual memory (bytes) snapshot=1457700864
		Total committed heap usage (bytes)=269484032
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=437
	File Output Format Counters 
		Bytes Written=197
bash-4.1# 
 

````

### 4.  Check the output

```bash
   bin/hdfs dfs -cat output/*

````

Output:

````aidl
    bash-4.1# bin/hdfs dfs -cat output/*
    6	dfs.audit.logger
    4	dfs.class
    3	dfs.server.namenode.
    2	dfs.period
    2	dfs.audit.log.maxfilesize
    2	dfs.audit.log.maxbackupindex
    1	dfsmetrics.log
    1	dfsadmin
    1	dfs.servers
    1	dfs.replication
    1	dfs.file

````



###  5. Exit by typing CONTROL-d (MAC) ??? (WINDOWS)
