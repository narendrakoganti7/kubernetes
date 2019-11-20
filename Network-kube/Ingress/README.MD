## Ingress

Collection of rules that will allow inbound connection 
to reach the cluster services.

* Ingress it self  not a load balance 
* Ingress it self not a physical representation 

It is logical controller that will be map to one of your load balance that ether 
cloud or physical or proprietary and its create set of rules this rules will route the traffic to runtime appropriate endpoints like (NodePort etc)  

### Configured to expose services through
* External URLs
* Load Balancers
* SSL terminated endpoints
* Name based virtual hosting

if you have set of pods that are expose to the outside wold through NodePort and you want clean mechanism to expose them and create set rule than you would create an ingress.

An Ingress is level above service particularly NodePort service and it is configured expose external url .

You can easy integrate with Nginx or HAproxy etc .. 
