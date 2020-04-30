## Namespace
The namespace is collect of objects like pods, deployments, service, Roles etc . namespace is an isolated environment for Kubernetes. Below are default namespaces.
- kube-system
- default
- kube-public

By default namespace is `default` . if you create any  object without mansion namespace it will create default namespce.


we can create namespaces for separate environments like prod and dev, test.

TO show all namespaces

`kubect get namespce`

To create new namespace

`kubectl create namespce dev`

To check pods under namespace 

`kubectl get pod namespace=dev`

or you can create namespace using yml definition file.

To change default namespace 

`kubectl config set-context $(kubectl config current-context) --namespace=dev`

To show all pods in cluster

`kubectl get pods --all-namespaces`

we can restrict resource for namespace using resource quota.
````
apiVersion: v1
kind: ResourceQuota
metadata:
  name: compute-quota
  namespace: dev
spec:
  hard:
    pods: "20"
    limits.memory: "1Gi"
````

