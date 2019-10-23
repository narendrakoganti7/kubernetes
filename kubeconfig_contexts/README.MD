## Kubeconfig contexts

*show kubeconfig contexts*

`kubectl config get-context`

*create context using kubectl cmd*

`kubectl config context contextname --namespace=kube-system --user=username --cluster=clustername`

*show current context*

`kubectl config current-contexts`

*switch context* 

`kubectl config use-context contextname` 

## change default config fie

 `./kube/config` is default config file for cluster and context so if you have custem config file then need replace the config file.
 
 please refer custom config [sample_config](https://github.com/narendrakoganti7/kubernetes/blob/master/kubeconfig_contexts/sample_config)
    

                        
                           
                           
