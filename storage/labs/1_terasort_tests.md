The full teragen and command you used and the job output
[hdfs@ip-172-31-15-25 root]$ time hadoop jar /opt/cloudera/parcels/CDH-5.11.2-1.cdh5.11.2.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapred.map.tasks=4 \-Ddfs.blocksize=33554432 10000000 /user/lannister/teragen5
17/10/03 14:02:38 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-14-187.us-west-2.compute.internal/172.31.14.187:8032
17/10/03 14:02:38 INFO terasort.TeraGen: Generating 10000000 using 4
17/10/03 14:02:38 INFO mapreduce.JobSubmitter: number of splits:4
17/10/03 14:02:38 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/03 14:02:38 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507048041067_0006
17/10/03 14:02:39 INFO impl.YarnClientImpl: Submitted application application_1507048041067_0006
17/10/03 14:02:39 INFO mapreduce.Job: The url to track the job: http://ip-172-31-14-187.us-west-2.compute.internal:8088/proxy/application_1507048041067_0006/
17/10/03 14:02:39 INFO mapreduce.Job: Running job: job_1507048041067_0006
17/10/03 14:02:45 INFO mapreduce.Job: Job job_1507048041067_0006 running in uber mode : false
17/10/03 14:02:45 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 14:02:58 INFO mapreduce.Job:  map 25% reduce 0%
17/10/03 14:02:59 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 14:02:59 INFO mapreduce.Job: Job job_1507048041067_0006 completed successfully
17/10/03 14:02:59 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=519780
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=337
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=46383
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=46383
                Total vcore-milliseconds taken by all map tasks=46383
                Total megabyte-milliseconds taken by all map tasks=47496192
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Input split bytes=337
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=566
                CPU time spent (ms)=28010
                Physical memory (bytes) snapshot=1521983488
                Virtual memory (bytes) snapshot=6371868672
                Total committed heap usage (bytes)=2438463488
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=21472776955442690
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=1000000000

real    0m23.464s
user    0m4.433s
sys     0m0.240s


The same for terasort
[hdfs@ip-172-31-15-25 root]$ time hadoop jar /opt/cloudera/parcels/CDH-5.11.2-1.cdh5.11.2.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/lannister/teragen5 /user/lannister/terasort1
17/10/03 14:04:18 INFO terasort.TeraSort: starting
17/10/03 14:04:19 INFO input.FileInputFormat: Total input paths to process : 4
Spent 121ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 124ms
Sampling 10 splits of 32
Making 12 from 100000 sampled records
Computing parititions took 510ms
Spent 636ms computing partitions.
17/10/03 14:04:20 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-14-187.us-west-2.compute.internal/172.31.14.187:8032
17/10/03 14:04:20 INFO mapreduce.JobSubmitter: number of splits:32
17/10/03 14:04:20 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507048041067_0007
17/10/03 14:04:21 INFO impl.YarnClientImpl: Submitted application application_1507048041067_0007
17/10/03 14:04:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-14-187.us-west-2.compute.internal:8088/proxy/application_1507048041067_0007/
17/10/03 14:04:21 INFO mapreduce.Job: Running job: job_1507048041067_0007
17/10/03 14:04:27 INFO mapreduce.Job: Job job_1507048041067_0007 running in uber mode : false
17/10/03 14:04:27 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 14:04:38 INFO mapreduce.Job:  map 3% reduce 0%
17/10/03 14:04:39 INFO mapreduce.Job:  map 22% reduce 0%
17/10/03 14:04:40 INFO mapreduce.Job:  map 53% reduce 0%
17/10/03 14:04:41 INFO mapreduce.Job:  map 72% reduce 0%
17/10/03 14:04:44 INFO mapreduce.Job:  map 75% reduce 0%
17/10/03 14:04:45 INFO mapreduce.Job:  map 91% reduce 0%
17/10/03 14:04:46 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 14:04:53 INFO mapreduce.Job:  map 100% reduce 8%
17/10/03 14:04:56 INFO mapreduce.Job:  map 100% reduce 50%
17/10/03 14:04:57 INFO mapreduce.Job:  map 100% reduce 58%
17/10/03 14:04:58 INFO mapreduce.Job:  map 100% reduce 100%
17/10/03 14:04:58 INFO mapreduce.Job: Job job_1507048041067_0007 completed successfully
17/10/03 14:04:58 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=443036415
                FILE: Number of bytes written=886093230
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1000003936
                HDFS: Number of bytes written=1000000000
                HDFS: Number of read operations=132
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=32
                Launched reduce tasks=12
                Data-local map tasks=32
                Total time spent by all maps in occupied slots (ms)=279434
                Total time spent by all reduces in occupied slots (ms)=112081
                Total time spent by all map tasks (ms)=279434
                Total time spent by all reduce tasks (ms)=112081
                Total vcore-milliseconds taken by all map tasks=279434
                Total vcore-milliseconds taken by all reduce tasks=112081
                Total megabyte-milliseconds taken by all map tasks=286140416
                Total megabyte-milliseconds taken by all reduce tasks=114770944
        Map-Reduce Framework
                Map input records=10000000
                Map output records=10000000
                Map output bytes=1020000000
                Map output materialized bytes=437273783
                Input split bytes=3936
                Combine input records=0
                Combine output records=0
                Reduce input groups=10000000
                Reduce shuffle bytes=437273783
                Reduce input records=10000000
                Reduce output records=10000000
                Spilled Records=20000000
                Shuffled Maps =384
                Failed Shuffles=0
                Merged Map outputs=384
                GC time elapsed (ms)=3988
                CPU time spent (ms)=172200
                Physical memory (bytes) snapshot=21348843520
                Virtual memory (bytes) snapshot=70055833600
                Total committed heap usage (bytes)=24882184192
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1000000000
        File Output Format Counters
                Bytes Written=1000000000
17/10/03 14:04:58 INFO terasort.TeraSort: done

real    0m40.932s
user    0m6.469s
sys     0m0.239s
