# Getting started with Minishift

Workshop content designed to be used by the [Workshopper tool](https://github.com/osevg/workshopper).

## Using this content

Either use the content directly by pointing at this repository

```
https://raw.githubusercontent.com/openshift-labs/minishift-guides/ocp-3.10/
```

## Create a full workshop

You can follow this instructions to create a full workshop site:

```
$ oc new-project guides
$ oc apply -f https://raw.githubusercontent.com/openshift-labs/minishift-guides/ocp-3.10/guides-template.yaml
$ oc new-app guide \
             -p CONSOLE_ADDRESS="https://master.osevg.openshiftworkshop.com"
             -p ROUTER_ADDRESS="apps.osevg.openshiftworkshop.com"
```

NOTE: You will need the following ENV values:

* *CONSOLE_ADDRESS*: Address to the master server's console
* *ROUTER_ADDRESS*: Wildcard DNS used for deployed apps

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
