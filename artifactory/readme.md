# How to: Push a Docker Image to Artifactory
```
export PROTOCOL=https
export ARTIFACTORY_DOMAIN=<artifactory_domain>                  # e.g. my-artifactory.com
export ARTIFACTORY_URL=${PROTOCOL}://${ARTIFACTORY_DOMAIN}      # e.g. https://my-artifactory.com
export REPOSITORY_NAME=<repository_name>                        # e.g. flbo-docker-local
export REPOSITORY_URL=${PROTOCOL}://${REPOSITORY_NAME}.${ARTIFACTORY_DOMAIN}
export IMAGE_NAME=<image_name>                                  # e.g. foobar
export IMAGE_VERSION=<image_version>                            # e.g. 1.0.0

docker login ${REPOSITORY_URL}
docker tag ${IMAGE_NAME}:${IMAGE_VERSION} ${REPOSITORY_NAME}.${ARTIFACTORY_DOMAIN}/${IMAGE_NAME}:${IMAGE_VERSION}
docker push ${REPOSITORY_NAME}.${ARTIFACTORY_DOMAIN}/${IMAGE_NAME}:${IMAGE_VERSION}
docker pull ${REPOSITORY_NAME}.${ARTIFACTORY_DOMAIN}/${IMAGE_NAME}:${IMAGE_VERSION}
```

# How to: Delete a Docker Image from Artifactory
```
curl --insecure -v -X DELETE -u "<user-name>:<password>" <artifactory-url>/<image-name>/<image-version>
```

# How to: Login to Artifactory Docker Registry
```
docker login ${REPOSITORY_PATH}.${ARTIFACTORY_URL}
```

# How to: Push a Helm Chart to Artifactory
```
# see also: https://gist.github.com/ipedrazas/b58c17fd10116b6d39935a6f11365214
curl --user $(PUBLISH_REPO_USER):$(PUBLISH_REPO_PWD) --upload-file $(PACKAGE) $(PUBLISH_REPO_URL)/$(PUBLISH_REPO_PATH)
```

