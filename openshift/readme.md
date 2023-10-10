# Grundlagen: Was ist der Unterschied zwischen einem Pod und einem Deployment oder Service
Siehe: https://stackoverflow.com/questions/41325087/what-is-the-difference-between-a-pod-and-a-deployment

# OpenShift Image Grundlagen
Siehe: https://docs.openshift.com/container-platform/4.2/openshift_images/create-images.html
Das wichtigste:
* OpenShift startet Container mit einer zufälligen UID
* diese zufälligen User sind aber immer Member der root Gruppe
* um permission Fehler zu vermeiden, müssen gewünschte Ordner also der root Gruppe zugewiesen werden und die Gruppe muss dann die entsprechenden Rechte bekommen

# How to: start a pod without manifest
```
kubectl run <pod_name> --image=<image_name> --restart=Never
```

# How to: connect to a container within an OC pod
```
# find the pod you want to connect to
oc get pods

# find the container within the pod you want to connect to
oc describe pod <name-of-your-pod>

oc rsh --container <container-name> <podname>
```


# Troubleshooting
```
oc get pods  
error: You must be logged in to the server (Unauthorized)

oc login
Login failed (401 Unauthorized)
Verify you have provided correct credentials.
```
Lösung:  
Prüfe das API Token, das in der kubeconfig hinterlegt ist. Ist es nocht korrekt?  
User Token updaten
```
USER=<user-name>
TOKEN=<user-api-token>
oc config set-credentials "${USER}" --token="${TOKEN}"
```
