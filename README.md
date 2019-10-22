# Install Kubernetes Using kubeadm

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
  
## Run kubectl init with pod network
 
 once successfuly install kubernetes packages then we need to run `kubectl init` command with pod network.
 
 here we selecting pod network as calico  network
 
  `kubectl init --pod-network=192.168.0.0/24`
  
  ## Install pod network calico
  
  `kubectl apply -f https://docs.projectcalico.org/v3.8/manifests/calico.yaml`
  
  
 
 
 