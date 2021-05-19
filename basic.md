

## Azure 



1. Setup Azure cli



#### Create a resource group

```
az group create --name sajithRG --location SoutheastAsia
```



#### Delete a resource group

```bash
az group delete --name sajithRG
```



#### Create Azure Container Registry

```
az acr create --resource-group sajithRG --name sajithacr --sku Basic
```



#### View Azure Container Registries

```
az acr list -o table	
```



```bash
sajith@sajith-dev:~/scratch/kube/echo_example$ az acr list -o table
NAME       RESOURCE GROUP    LOCATION       SKU    LOGIN SERVER          CREATION DATE         ADMIN ENABLED
---------  ----------------  -------------  -----  --------------------  --------------------  ---------------
sajithACR  sajithRG          southeastasia  Basic  sajithacr.azurecr.io  2020-12-28T15:23:08Z  False
```



#### View ACR server name

```
az acr list --resource-group sajithRG --query "[].{acrLoginServer:loginServer}" --output table
```



#### View images in ACR

```bash
sajith@sajith-dev:~/scratch/kube/echo_example$ az acr repository list --name sajithacr --output table
Result
-----------
python-echo

```



#### Create Kube cluster

``` bash
az aks create \
    --resource-group sajithRG \
    --name sajithcluster \
    --node-count 2 \
    --generate-ssh-keys \
    --attach-acr sajithacr
```





#### Using kubectl

Read the documentation, you can get the secreats and then use kubeclt as usual



### Create API Managment



``` bash
az apim create --name sajithapim --resource-group sajithRG \
  --publisher-name Hyperion --publisher-email admin@hyperion.com \
  --no-wait
```



#### View APIM

```bash
sajith@sajith-dev:~/scratch/kube/echo_azure$ az apim  list -o table
Command group 'apim' is in preview. It may be changed/removed in a future release.
NAME        RESOURCE GROUP    LOCATION        GATEWAY ADDR    PUBLIC IP    PRIVATE IP    STATUS      TIER       UNITS
----------  ----------------  --------------  --------------  -----------  ------------  ----------  ---------  -------
sajithapim  sajithRG          Southeast Asia                                             Activating  D
```

