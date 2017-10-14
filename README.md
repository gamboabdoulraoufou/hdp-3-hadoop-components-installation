### hdp-3-hadoop-components-installation


> Configuration
- 4 VMs on google compute Engine (3 VM for Hadoop Cluster and 1 VM for data backup and micro services)
- OS: CentOS 7
- RAM: 15 Go
- CPU: 4
- Boot disk: 200Go
- Attached disk: 2000G

> Cluster model

![MetaStore remote database](https://github.com/gamboabdoulraoufou/hdp-1-host-config/blob/master/img/archi_v2.png)


> Connecte to Ambari web UI

- Go to http://IP:8080 or http://hostname:8080
- Login: admin
- Password: admin

![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-2-ambari-and-hadoop-components-installation/blob/master/img/ambari_ui.png)


> Follow the step bellow to install cluster

![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-1.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-2.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-3.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-4.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-5.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-6.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-7.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-8.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-10-1.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-10-2.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-10-3.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-10-4.png)
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-10-5.png)

> Enjoy
![Ambari-config](https://github.com/gamboabdoulraoufou/hdp-4-hadoop-components-installation/blob/master/img/hdp-3-12.png)



> Configure Hadoop core services auto-start at Cluster nodes boot

```sh
# create script folder 
mkdir /root/process

# create file
vi /root/process/start_hdp_services.sh

# add the following content
#### START ####
#!/bin/sh

PASSWORD=admin
CLUSTER_NAME=hdp_pre_prod

# Run some ambari service on start up
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start HDFS via REST"}, "Body": {"ServiceInfo":{"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/HDFS
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start YARN via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/YARN
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start MAPREDUCE2 via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/MAPREDUCE2
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start TEZ via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/TEZ
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start HIVE via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/HIVE
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start PIG via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/PIG
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start SQOOP via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/SQOOP
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start OOZIE via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/OOZIE
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start ZOOKEEPER via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/ZOOKEEPER
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start AMBARI_METRICS via REST"}, "Body": {"ServiceInfo":{"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/AMBARI_METRICS
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start SPARK via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/SPARK
curl -u admin:$PASSWORD -i -H 'X-Requested-By: ambari' -X PUT -d '{"RequestInfo": {"context" :"Start SLIDER via REST"}, "Body": {"ServiceInfo": {"state": "STARTED"}}}' http://localhost:8080/api/v1/clusters/hadoop/services/SLIDER

#### END ####

# save and quit
# configure crontab
crontab -e 

# add the follwing lines
#### START ####
# start hdp services
@reboot sleep 180; sh /root/process/start_hdp_services.sh
#### END ####

# save and quit

```
> Confi
> Troubleshooting with oozie
```sh
wget  http://velvet-repo.c.equipe-1314.internal/repo/HDP-UTILS/extjs/extjs-2.2-1.noarch.rpm
chmod +x extjs-2.2-1.noarch.rpm 
rpm -ivh extjs-2.2-1.noarch.rpm
```
