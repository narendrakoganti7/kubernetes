# User management ( Roles)

when you  want to  give access for user in kubernetes , fist we need to create namespace 

`kubectl create namespace dev`

**or using yaml file**

[sample_yamlcode](https://github.com/narendrakoganti7/kubernetes/blob/master/KUBE_AUTH_ROLES/namespace.yaml)

## create certificates for new users 
 We need to create private key for user
 
`openssl genrsa -out developer.key 2048` 

then need to create certificate request 

`openssl req -new -key developer.key -out developer.csr -subj "/CN=developer/o=javadevloper"`

we need to approve csr certificate to kubernetes certificate authority.

`openssl x509 -req -in developer.csr -CA /etc/kubernetes/pki/ca.crt -CAkey /etc/kubernetes/pki/ca.key -CAcreateserial -out developer.crt -days 500 `

 **create role using yaml**
   [kube-role-dev](https://github.com/narendrakoganti7/kubernetes/blob/master/KUBE_AUTH_ROLES/kube-role-dev.yaml)
   
   `kubectl create -f kube-role-dev.yaml`

already we created role then need to create rolebind

rolebinding is bind role and user.

please check below yaml file 

[Rolebinding_dev](https://github.com/narendrakoganti7/kubernetes/blob/master/KUBE_AUTH_ROLES/RoleBinding.yaml)

### Method 1: this way not recommended method
this way we can generate .kube/config

create user credentials using kubectl

`kubectl config set-credentials developer --client-certificate=/home/gcp/kubernetes/KUBE_AUTH_ROLES/users/devloper/developer.crt --client-key=/home/gcp/kubernetes/KUBE_AUTH_ROLES/users/devloper/devloper.key`

create  new context for dev user

`kubectl config set-context dev-context --cluster=kubernetes --namespace=development --user=developer` 

the copy .kube/config and edit according to developer context
remove admin contaxt and copy to user home directory .

### Method 2:

you can write your self config yaml file
  * sample : [sample_config_user](https://github.com/narendrakoganti7/kubernetes/blob/master/KUBE_AUTH_ROLES/developer_config) 
  
  copy custom config to user home directory