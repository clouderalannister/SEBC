[root@ip-172-31-14-187 ~]# sh -x /disco1/YARNtest.sh
+ MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
+ HADOOP=/opt/cloudera/parcels/CDH/bin
++ date
+ echo Testing loop started on Tue Oct 3 17:05:07 EDT 2017
Testing loop started on Tue Oct 3 17:05:07 EDT 2017
+ for i in 8
+ for j in 1
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 51200000 /user/lannister/results/tg-10GB-8-1-512

real    0m2.368s
user    0m3.273s
sys     0m0.168s
+ echo 'job map' 8
job map 8
+ echo 'map memory' 512
map memory 512
+ echo 'max heap java' 409
max heap java 409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 /user/lannister/results/tg-10GB-8-1-512 /user/lannister/results/ts-10GB-8-1-512

real    0m2.360s
user    0m3.208s
sys     0m0.179s
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-8-1-512
rm: `/results/tg-10GB-8-1-512': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-8-1-512
rm: `/results/ts-10GB-8-1-512': No such file or directory
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 51200000 /user/lannister/results/tg-10GB-8-1-1024

real    0m2.395s
user    0m3.485s
sys     0m0.196s
+ echo 'job map' 8
job map 8
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap java' 819
max heap java 819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 /user/lannister/results/tg-10GB-8-1-1024 /user/lannister/results/ts-10GB-8-1-1024

real    0m2.172s
user    0m2.774s
sys     0m0.166s
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-8-1-1024
rm: `/results/tg-10GB-8-1-1024': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-8-1-1024
rm: `/results/ts-10GB-8-1-1024': No such file or directory
++ date
+ echo Testing loop ended on Tue Oct 3 17:05:25 EDT 2017
Testing loop ended on Tue Oct 3 17:05:25 EDT 2017
[root@ip-172-31-14-187 ~]# vi /disco1/YARNtest.sh
[root@ip-172-31-14-187 ~]# time sh -x /disco1/YARNtest.sh
+ MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
+ HADOOP=/opt/cloudera/parcels/CDH/bin
++ date
+ echo Testing loop started on Tue Oct 3 17:12:00 EDT 2017
Testing loop started on Tue Oct 3 17:12:00 EDT 2017
+ for i in 4 8
+ for j in 1 4
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 51200000 /user/lannister/results/tg-10GB-4-1-512

real    0m2.538s
user    0m3.705s
sys     0m0.165s
+ echo 'job map' 4
job map 4
+ echo 'map memory' 512
map memory 512
+ echo 'max heap java' 409
max heap java 409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 /user/lannister/results/tg-10GB-4-1-512 /user/lannister/results/ts-10GB-4-1-512

real    0m2.216s
user    0m2.896s
sys     0m0.163s
+ echo 'job map' 4
job map 4
+ echo 'job reduce' 1
job reduce 1
+ echo 'map memory' 512
map memory 512
+ echo 'max heap' 409
max heap 409
+ echo 'memory reduce' 512
memory reduce 512
+ echo 'java max heap' 409
java max heap 409
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-4-1-512
rm: `/results/tg-10GB-4-1-512': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-4-1-512
rm: `/results/ts-10GB-4-1-512': No such file or directory
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 51200000 /user/lannister/results/tg-10GB-4-1-1024

real    0m2.419s
user    0m3.402s
sys     0m0.191s
+ echo 'job map' 4
job map 4
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap java' 819
max heap java 819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 /user/lannister/results/tg-10GB-4-1-1024 /user/lannister/results/ts-10GB-4-1-1024

real    0m2.151s
user    0m2.733s
sys     0m0.150s
+ echo 'job map' 4
job map 4
+ echo 'job reduce' 1
job reduce 1
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap' 819
max heap 819
+ echo 'memory reduce' 1024
memory reduce 1024
+ echo 'java max heap' 819
java max heap 819
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-4-1-1024
rm: `/results/tg-10GB-4-1-1024': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-4-1-1024
rm: `/results/ts-10GB-4-1-1024': No such file or directory
+ for j in 1 4
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 51200000 /user/lannister/results/tg-10GB-4-4-512

real    0m2.428s
user    0m3.376s
sys     0m0.177s
+ echo 'job map' 4
job map 4
+ echo 'map memory' 512
map memory 512
+ echo 'max heap java' 409
max heap java 409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=4 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 /user/lannister/results/tg-10GB-4-4-512 /user/lannister/results/ts-10GB-4-4-512

real    0m2.285s
user    0m3.041s
sys     0m0.158s
+ echo 'job map' 4
job map 4
+ echo 'job reduce' 4
job reduce 4
+ echo 'map memory' 512
map memory 512
+ echo 'max heap' 409
max heap 409
+ echo 'memory reduce' 512
memory reduce 512
+ echo 'java max heap' 409
java max heap 409
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-4-4-512
rm: `/results/tg-10GB-4-4-512': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-4-4-512
rm: `/results/ts-10GB-4-4-512': No such file or directory
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 51200000 /user/lannister/results/tg-10GB-4-4-1024

real    0m2.326s
user    0m3.188s
sys     0m0.164s
+ echo 'job map' 4
job map 4
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap java' 819
max heap java 819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=4 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 /user/lannister/results/tg-10GB-4-4-1024 /user/lannister/results/ts-10GB-4-4-1024

real    0m2.202s
user    0m2.872s
sys     0m0.147s
+ echo 'job map' 4
job map 4
+ echo 'job reduce' 4
job reduce 4
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap' 819
max heap 819
+ echo 'memory reduce' 1024
memory reduce 1024
+ echo 'java max heap' 819
java max heap 819
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-4-4-1024
rm: `/results/tg-10GB-4-4-1024': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-4-4-1024
rm: `/results/ts-10GB-4-4-1024': No such file or directory
+ for i in 4 8
+ for j in 1 4
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 51200000 /user/lannister/results/tg-10GB-8-1-512

real    0m2.450s
user    0m3.306s
sys     0m0.177s
+ echo 'job map' 8
job map 8
+ echo 'map memory' 512
map memory 512
+ echo 'max heap java' 409
max heap java 409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 /user/lannister/results/tg-10GB-8-1-512 /user/lannister/results/ts-10GB-8-1-512

real    0m2.309s
user    0m3.182s
sys     0m0.170s
+ echo 'job map' 8
job map 8
+ echo 'job reduce' 1
job reduce 1
+ echo 'map memory' 512
map memory 512
+ echo 'max heap' 409
max heap 409
+ echo 'memory reduce' 512
memory reduce 512
+ echo 'java max heap' 409
java max heap 409
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-8-1-512
rm: `/results/tg-10GB-8-1-512': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-8-1-512
rm: `/results/ts-10GB-8-1-512': No such file or directory
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 51200000 /user/lannister/results/tg-10GB-8-1-1024

real    0m2.317s
user    0m3.271s
sys     0m0.180s
+ echo 'job map' 8
job map 8
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap java' 819
max heap java 819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 /user/lannister/results/tg-10GB-8-1-1024 /user/lannister/results/ts-10GB-8-1-1024

real    0m2.189s
user    0m2.862s
sys     0m0.172s
+ echo 'job map' 8
job map 8
+ echo 'job reduce' 1
job reduce 1
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap' 819
max heap 819
+ echo 'memory reduce' 1024
memory reduce 1024
+ echo 'java max heap' 819
java max heap 819
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-8-1-1024
rm: `/results/tg-10GB-8-1-1024': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-8-1-1024
rm: `/results/ts-10GB-8-1-1024': No such file or directory
+ for j in 1 4
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 51200000 /user/lannister/results/tg-10GB-8-4-512

real    0m2.312s
user    0m3.167s
sys     0m0.160s
+ echo 'job map' 8
job map 8
+ echo 'map memory' 512
map memory 512
+ echo 'max heap java' 409
max heap java 409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=4 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 /user/lannister/results/tg-10GB-8-4-512 /user/lannister/results/ts-10GB-8-4-512

real    0m2.201s
user    0m2.849s
sys     0m0.169s
+ echo 'job map' 8
job map 8
+ echo 'job reduce' 4
job reduce 4
+ echo 'map memory' 512
map memory 512
+ echo 'max heap' 409
max heap 409
+ echo 'memory reduce' 512
memory reduce 512
+ echo 'java max heap' 409
java max heap 409
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-8-4-512
rm: `/results/tg-10GB-8-4-512': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-8-4-512
rm: `/results/ts-10GB-8-4-512': No such file or directory
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 51200000 /user/lannister/results/tg-10GB-8-4-1024

real    0m2.431s
user    0m3.426s
sys     0m0.172s
+ echo 'job map' 8
job map 8
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap java' 819
max heap java 819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=4 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 /user/lannister/results/tg-10GB-8-4-1024 /user/lannister/results/ts-10GB-8-4-1024

real    0m2.211s
user    0m2.886s
sys     0m0.182s
+ echo 'job map' 8
job map 8
+ echo 'job reduce' 4
job reduce 4
+ echo 'map memory' 1024
map memory 1024
+ echo 'max heap' 819
max heap 819
+ echo 'memory reduce' 1024
memory reduce 1024
+ echo 'java max heap' 819
java max heap 819
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/tg-10GB-8-4-1024
rm: `/results/tg-10GB-8-4-1024': No such file or directory
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /results/ts-10GB-8-4-1024
rm: `/results/ts-10GB-8-4-1024': No such file or directory
++ date
+ echo Testing loop ended on Tue Oct 3 17:13:12 EDT 2017
Testing loop ended on Tue Oct 3 17:13:12 EDT 2017

real    1m11.987s
user    1m36.966s
sys     0m5.283s
[root@ip-172-31-14-187 ~]# vi /disco1/YARNtest.sh
[root@ip-172-31-14-187 ~]# Write failed: Connection reset by peer
