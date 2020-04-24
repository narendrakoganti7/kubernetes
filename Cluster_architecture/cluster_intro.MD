## kubernetes Architecture compounds

* ETCD
* KUBE-API Server
* Controller Manager
* Kube Scheduler
* kubelet
* kube proxy

**ETCD:**

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

## Kube-API SERVER:



Kube-API server is primary management component in Kubernetes. When you run kubctl command, kubctl utility reaches to the API server and first authenticate the request and validated then retrieves the data from ETCD and response back to kubectl.

When you want to create a pod, then Kube api server contact with scheduler and find the right worker node communicate back to the api server, and api server updates the information into etcd. Api server passes the info into kubelet. kubelet create the pod and update back to api server then api server updates in etcd.

*below steps are involved in api server*

* Authenticate user
* Validate request
* Retrieves data
* Update ETCD
* Scheduler 
* Kubelet