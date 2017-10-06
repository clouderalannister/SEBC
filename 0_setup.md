AWS

ec2-34-209-149-187.us-west-2.compute.amazonaws.com
ec2-54-191-198-136.us-west-2.compute.amazonaws.com	ip-172-31-15-15.us-west-2.compute.internal
ec2-54-149-72-173.us-west-2.compute.amazonaws.com	ip-172-31-9-36.us-west-2.compute.internal
ec2-34-212-140-167.us-west-2.compute.amazonaws.com	ip-172-31-2-49.us-west-2.compute.internal

Red Hat Enterprise Linux Server release 6.7 (Santiago)

[root@ip-172-31-15-86 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, security
rhui-REGION-client-config-server-6                                                                                                                 | 2.9 kB     00:00
rhui-REGION-client-config-server-6/primary_db                                                                                                      | 7.1 kB     00:00
rhui-REGION-rhel-server-releases                                                                                                                   | 3.5 kB     00:00
rhui-REGION-rhel-server-releases/primary_db                                                                                                        |  58 MB     00:00
rhui-REGION-rhel-server-rh-common                                                                                                                  | 3.8 kB     00:00
rhui-REGION-rhel-server-rh-common/primary_db                                                                                                       |  65 kB     00:00
repo id                                                            repo name                                                                                        status
rhui-REGION-client-config-server-6                                 Red Hat Update Infrastructure 2.0 Client Configuration Server 6                                       8
rhui-REGION-rhel-server-releases                                   Red Hat Enterprise Linux Server 6 (RPMs)                                                         19,774
rhui-REGION-rhel-server-rh-common                                  Red Hat Enterprise Linux Server 6 RH Common (RPMs)                                                  129
repolist: 19,911

useradd -u 2800 saturn
useradd -u 2900 haley

groupadd comets
groupadd planets
usermod -g comets haley
usermod -g planets saturn

tcpdump:x:72:72::/:/sbin/nologin
ec2-user:x:500:500::/home/ec2-user:/bin/bash
saturn:x:2800:2902::/home/saturn:/bin/bash
haley:x:2900:2901::/home/haley:/bin/bash


ec2-user:x:500:
saturn:x:2800:
haley:x:2900:
comets:x:2901:
planets:x:2902:

rpm -ivh mysql57-community-release-el6-11.noarch.rpm
yum install mysql mysql-server
yum install mysql

[root@ip-172-31-2-49 disco1]# rpm -ivh mysql57-community-release-el6-11.noarch.rpm
warning: mysql57-community-release-el6-11.noarch.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ########################################### [100%]
   1:mysql57-community-relea########################################### [100%]
[root@ip-172-31-2-49 disco1]# yum install mysql
Loaded plugins: amazon-id, rhui-lb, security
Setting up Install Process
mysql-connectors-community                                                                                                                         | 2.5 kB     00:00
mysql-connectors-community/primary_db                                                                                                              |  17 kB     00:00
mysql-tools-community                                                                                                                              | 2.5 kB     00:00
mysql-tools-community/primary_db                                                                                                                   |  37 kB     00:00
mysql57-community                                                                                                                                  | 2.5 kB     00:00
mysql57-community/primary_db                                                                                                                       | 120 kB     00:00
rhui-REGION-client-config-server-6                                                                                                                 | 2.9 kB     00:00
rhui-REGION-client-config-server-6/primary_db                                                                                                      | 7.1 kB     00:00
rhui-REGION-rhel-server-releases                                                                                                                   | 3.5 kB     00:00
rhui-REGION-rhel-server-releases/primary_db                                                                                                        |  58 MB     00:00
rhui-REGION-rhel-server-rh-common                                                                                                                  | 3.8 kB     00:00
rhui-REGION-rhel-server-rh-common/primary_db                                                                                                       |  65 kB     00:00


[root@ip-172-31-9-130 java]# mysql -u root -pLannister2017
mysql: [Warning] World-writable config file '/etc/my.cnf' is ignored.
mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 13
Server version: 5.7.19 MySQL Community Server (GPL)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> select @@hostname;
+--------------------------------------------+
| @@hostname                                 |
+--------------------------------------------+
| ip-172-31-9-130.us-west-2.compute.internal |
+--------------------------------------------+
1 row in set (0.00 sec)

mysql> SHOW VARIABLES LIKE "%version%";
+-------------------------+------------------------------+
| Variable_name           | Value                        |
+-------------------------+------------------------------+
| innodb_version          | 5.7.19                       |
| protocol_version        | 10                           |
| slave_type_conversions  |                              |
| tls_version             | TLSv1,TLSv1.1                |
| version                 | 5.7.19                       |
| version_comment         | MySQL Community Server (GPL) |
| version_compile_machine | x86_64                       |
| version_compile_os      | Linux                        |
+-------------------------+------------------------------+
8 rows in set (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| sentry             |
| sys                |
+--------------------+
9 rows in set (0.00 sec)

mysql>

[root@ip-172-31-9-130 java]# ls /etc/yum.repos.d
mysql-community.repo  mysql-community-source.repo  redhat.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhel-source.repo  rhui-load-balancers.conf

[root@ip-172-31-15-15 schema]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-9-130.us-west-2.compute.internal -utemp -ptemp  clouderameta temp temp
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Fri Oct 06 12:05:34 EDT 2017 WARN: Establishing SSL connection without server's identity verification is not recommended. According to MySQL 5.5.45+, 5.6.26+ and 5.7.6+ requirements SSL connection must be established by default if explicit option isn't set. For compliance with existing applications not using SSL the verifyServerCertificate property is set to 'false'. You need either to explicitly disable SSL by setting useSSL=false, or set useSSL=true and provide truststore for server certificate verification.
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
Fri Oct 06 12:05:34 EDT 2017 WARN: Establishing SSL connection without server's identity verification is not recommended. According to MySQL 5.5.45+, 5.6.26+ and 5.7.6+ requirements SSL connection must be established by default if explicit option isn't set. For compliance with existing applications not using SSL the verifyServerCertificate property is set to 'false'. You need either to explicitly disable SSL by setting useSSL=false, or set useSSL=true and provide truststore for server certificate verification.
2017-10-06 12:05:35,224 [main] INFO  com.cloudera.enterprise.dbutil.DbCommandExecutor  - Successfully connected to database.
All done, your SCM database is configured correctly!


2017-10-06 12:08:12,523 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.

[root@ip-172-31-15-15 schema]# more /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri Oct  6 12:05:34 EDT 2017
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=ip-172-31-9-130.us-west-2.compute.internal
com.cloudera.cmf.db.name=clouderameta
com.cloudera.cmf.db.user=temp
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=temp
