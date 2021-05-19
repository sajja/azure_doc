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





