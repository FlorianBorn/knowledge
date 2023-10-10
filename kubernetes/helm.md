# How to: Install (deploy) a helm chart
```
helm install [-f <path-to-values.yaml>] <release-name> <path-to-helm-chart-directory-or-url-to-packaged-helm-chart>
```

# How to: Build a Helm Package
```
export PACKAGE_VERSION=0.0.1 # set your package version here

cd /path/to/helm/chart
helm dependency update .
helm package . --version 0.0.1
```

# How to: Download a Helm Chart
```
export HELM_CHART_REPO=<helm-chart-repo>
export HELM_CHART_NAME=<chart-name>
export HELM_CHART_VERSION=<helm-chart-version>
helm pull --repo ${HELM_CHART_REPO} --version ${HELM_CHART_VERSION} --untar --untardir . ${HELM_CHART_NAME}
```

# How to: Install and Test a Helm Chart
```
export RELEASE_NAME=sorry-cypress-local

helm install --values pipeship/chart/values.yaml ${RELEASE_NAME} pipeship/chart/

helm test --logs ${RELEASE_NAME}

helm upgrade sorry-cypress-local pipeship/chart/
```