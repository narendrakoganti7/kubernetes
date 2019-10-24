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


  