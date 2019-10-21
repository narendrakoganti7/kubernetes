#Install Kubernetes Using kubeadm

This installation document  for one master and two worker nodes


  * Setup vm instance
  * Install docker using script for all nodes
  * Install kubeadm, kubectl, kubelet for all nodes
  * Exucet kubeclt inti command run only master
  * Create pod network on master node
  
  ## Setup VM instance
  We need to setup 3 vm on your pc or public cloud enverment.
  need to assinge  static ip for all nodes
  
  select os centos/ubuntu linux .
  
  ## Install docker 
  
  Clone rep and exuce blewo scrip
  `chmod 744 install_docker_kubernetes.sh`
  `./install_docker_kubernetes.sh`
  
  ## Install kube tools
  
  excute kuberinstall script
  `chmod 744 kubetools.sh`
  `./kubetools.sh`
  
