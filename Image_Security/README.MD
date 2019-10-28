## Image security

Image security main focus is store the private repository details like DNS server name and username,password
then inject store data into yaml files.

* step 1:
          store the Private repository details in secret object
          
     `kubectl create secret docker-registry regcred --docker-server=server --docker-user=usernaem --docker-password=password --docker-email= nar@email.com`
 * step 2:
         
     inject secret data into pod/ deployments
         
      sample code [image-security](https://github.com/narendrakoganti7/kubernetes/blob/master/Image_Security/Image-security.yaml)