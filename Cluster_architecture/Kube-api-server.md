## Kube-API SERVER:



Kube-API server is primary management component in Kubernetes. When you run kubctl command, kubctl utility reaches to the API server and first authenticate the request and validated then retrieves the data from ETCD and response back to kubectl.

When you want to create a pod, then Kube api server contact with scheduler and find the right worker node communicate back to the api server, and api server updates the information into etcd. Api server passes the info into kubelet. kubelet create the pod and update back to api server then api server updates in etcd. kube api server only one directly communicate with ETCD

*below steps are involved in api server*

* Authenticate user
* Validate request
* Retrieves data
* Update ETCD
* Scheduler 
* Kubelet