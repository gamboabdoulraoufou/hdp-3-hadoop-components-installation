### hdp-3-hadoop-components-installation


> Configuration
- 4 VMs on google compute Engine (3 VM for Hadoop Cluster and 1 VM for data backup and micro service)
- OS: CentOS 6
- RAM: 15Go
- CPU: 4
- Boot disk: 100Go
- Attached disk: 200G

> Cluster model

![MetaStore remote database](https://github.com/gamboabdoulraoufou/hdp-1-host-config/blob/master/img/archi.png)

> 





oozie issue
wget  http://velvet-repo.c.equipe-1314.internal/repo/HDP-UTILS/extjs/extjs-2.2-1.noarch.rpm
chmod +x extjs-2.2-1.noarch.rpm 
rpm -ivh extjs-2.2-1.noarch.rpm


python /usr/lib/python2.6/site-packages/ambari_agent/HostCleanup.py --silent --skip=users
