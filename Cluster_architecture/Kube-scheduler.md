## Kube-scheduler

Kube-scheduler was responsible for schedule a pod on nodes. The scheduler is only responsible for deciding which Pod goes on which node then kubelete create Pod within the node. The scheduler never creates pods. 