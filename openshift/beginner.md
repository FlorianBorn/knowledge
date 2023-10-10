# How to: create a simple deployment on Openshift
```
export example_folder=oc_spielwiese
export deployment_file=deployment.yml

mkdir ${example_folder}

cd ${example_folder}

cat <<HERE > ${deployment_file}
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 2 # tells deployment to run 2 pods matching the template
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
HERE

oc apply -f ${deployment_file}

```