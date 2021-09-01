# Kogito Workshop

Last update: Process Automation 7.11


## Instructions

### Running locally

Running locally with Docker:

```
docker run -it --rm -p 8080:8080 -v $(pwd):/app-data -e CONTENT_URL_PREFIX="file:///app-data" -e WORKSHOPS_URLS="file:///app-data/_kogito_workshop.yml" -e LOG_TO_STDOUT=true quay.io/osevg/workshopper
```

Running locally with Podman:

```sh
podman run -it --rm -p 8080:8080 -v .:/app-data:Z -e CONTENT_URL_PREFIX="file:///app-data" -e WORKSHOPS_URLS="file:///app-data/_kogito_workshop.yml" -e LOG_TO_STDOUT=true quay.io/osevg/workshopper
```

### Running on ocp

Login on ocp and:

````
oc create -f support/ocp-provisioning.yml
````
