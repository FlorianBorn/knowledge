# See: https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/

# How to: Create a configmap with kubectl (in an existing cluster)
```
kubectl create configmap <configmap-name> --from-file=<path-to-file>

kubectl get configmaps

kubectl describe configmaps <configmap-name>
```