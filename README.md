## Configure Jenkins CI on Azure
----
1. Get a free subscription
2. Open Azure Terminal from Portal
* Create resource group
```
az group create -name <ResourceGroupName> -location westeurope
```
* Deploy azure container to the current resource group. 
Specify image from https://hub.docker.com/ or other repo, open ports and set the public ip-address
```
az container create -g <ResourceGroupName> -n <InstanceName> --image jenkins --ports 8080 --ip-address public
```
5. Access the container filesystem in order to unlock Jenkins
``` 
az container exec -g <ResourceGroupName> -n <InstanceName> --exec-command "/bin/bash"
```
6. Configure your CI
