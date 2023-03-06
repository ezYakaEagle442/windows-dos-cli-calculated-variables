# windows-dos-cli-calculated-variables


```sh
FOR /F %i IN ('az deployment group show --name dummy  -g rg-dummy --query properties.outputs.fooName.value -o tsv') DO set FOO=%i

az redis list-keys -n %FOO% -g rg-dummy 
```
