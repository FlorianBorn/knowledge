# How to: Create a secret with kubectl
See: https://kubernetes.io/docs/concepts/configuration/secret/
```
# hiermit wird ein secret vom Typ 'opaque' mit dem Namen 'my-secret' erstellt
kubectl create secret generic my-secret --from-literal=MY_KEY=my_value
kubectl get secret my-secret
```

# How to: Pass a K8S Secret as Env-Variable to a Docker Container
See: https://medium.com/@milindawelagedara/pass-database-username-and-password-as-environment-variables-to-kubernetes-deployment-using-392b27934f60