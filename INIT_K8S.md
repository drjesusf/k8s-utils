INIT_K8S.md

Ingresar al portal de azure
Seleccionar como linea de comandos a la shell de azure

- az login
- az aks get-credentials --resource-group [nombre-del-grupo] --name [nombre-del-cluster]
- kubectl config set-context --current --namespace=rper
- kubectl get pods
