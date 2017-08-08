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




> Troubleshooting with oozie
```sh
wget  http://velvet-repo.c.equipe-1314.internal/repo/HDP-UTILS/extjs/extjs-2.2-1.noarch.rpm
chmod +x extjs-2.2-1.noarch.rpm 
rpm -ivh extjs-2.2-1.noarch.rpm
```
