## ReplicaSet

Replicaset provides high availability for application pods. Even you can use replicaset minimum of one pod if that pod crashes then it will automatically create the new pod. Based on demand, we can increase the number of pods in replicaset. If the usage of application is more, we can add nodes in the replicaset.

````
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: httpd-rp
  labels:
    app: web
spec:
  template:
    metadata:
      name: httpd
      labels: # must enter labels in replica set
        app: web-server
        type: php r 
    spec:
      containers:
        - name: httpd-app
          image: httpd
  replicas: 2
# In Replica set selector is mandarty object. Replica set alwasys monitor pods based on matchlabls.
  selector: 
    matchLabels:
      type: php

````

*To get replicaset information*

`kubectl get replicaset`

*To scale replicaset*

`kubectl scale --replicas=3 -f replicaset.yml`

or

`kubectl scale --replicas=3 replicaset nameofreplicaset`


### Replica controller
replica controller aslo same like replicaset but don't have `selector` and `lables` opption 

