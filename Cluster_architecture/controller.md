## controller manager

A controller is a process that continuously monitors the state of various components. For example, Node-controller is responsible for overseeing the status of worker nodes and taking the necessary actions to keep the application run. It does that through the Kube-api server. The node controller checks the state of the node every 5s that way node controller health of the nodes. Like a node controller, Kubernetes have many controllers(Replicated controller, Role controller, Namespace controller, service account controller). The controller manager is the brain of Kubernetes. All controllers handled the controller manager's service. 

We can install the controller manager from the Kubernetes download website.

`kube-controller-manager.service` you can customize controllers here.like 
```
node-monitoring-periond=5s
node-monitoring-grace-period=45s  
```

 we have additional options like enable controllers and disable controllers, by default it allows all controllers

`--controllers stringlice   Default:[*]`

we can check controller manager status

`kubectl get pods -n kube-system`
