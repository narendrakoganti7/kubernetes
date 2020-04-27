## etcd:

ETCD is a key-value store. It has stored data into a database. it can download from Github. To start ETCD ./etcd command, when starting service it opens port 2379 and runs etcdclt client. 

*key value example*

 key | value 
--- | --- 
pod1 | oracle 
pod2 | java

*etcd example commands*
 
`./etcdctl set key1 value1`

*To retrieve data from etcd*

`./etcdctl get key1`

**ETCD Role in Kubernetes:**

Nods, Pods, Configs, Roles, Accounts, Bindings etc .. are stored into ETCD. Every change you made into cluster they were updated into ETCD. When you run `kubctl get value` command, it gets data from ETCD database.If you want to install Kubernetes in a hard way then ETCD we need to invest as service and manually configure TLS certificates. If it is kubeadm method, then ETCD is a container. 
In HA configuration in  master nodes, each master have separate  ETCD
