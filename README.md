# windows-dos-cli-calculated-variables


```sh
FOR /F %i IN ('az deployment group show --name dummy  -g rg-dummy --query properties.outputs.fooName.value -o tsv') DO set FOO=%i

az redis list-keys -n %FOO% -g rg-dummy 
```


@echo on
REM tokens=n     The numbered items to  read from each line. Default = 1.

(FOR /F "skip=2 tokens=1-2,2" %%i IN ('az ad app list --show-mine --query "[?displayName=='%SPN_APP_NAME%'].{objectId:id}"') DO (
    echo "%%i %%j"
    IF "%%i"==""objectId":" SET SPN_APP_ID=%%j
))
az ad app show --id %SPN_APP_ID%
