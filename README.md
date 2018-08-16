# Getting started with Minishift

Workshop content designed to be used by the [Workshopper tool](https://github.com/osevg/workshopper).

# Run Guides Locally
```
$ git clone https://github.com/openshift-labs/minishift-guides.git
$ cd minishift-guides

$ docker run -it --rm -p 8080:8080 -v $(pwd):/app-data \
              -e CONTENT_URL_PREFIX="file:///app-data" \
              -e LOG_TO_STDOUT=true \
              -e WORKSHOPS_URLS="file:///app-data/_workshops/minishift-guides.yml" \
              quay.io/osevg/workshopper:latest 
```
