## 2.0.1

ENHANCEMENTS:

* Changed the defaults of service accounts for running the satellite. This wil prevent insufficient errors when running the pods
* Updated the default resources to match in-line with the recommended memory usage

## 2.0.0

This repo is a fork of [lightstep-satellite-helm-chart](https://github.com/lightstep/lightstep-satellite-helm-chart/) for Lightstep microsatellites. Everything version 2.0.0 and after will be for microsatellites only.

Breaking changes:
- Point repository to [lightstep/microsatellite](https://hub.docker.com/r/lightstep/microsatellite)
- Bump version to `2021-03-22_13-16-05Z`
- Remove optional config `bytes_per_project` (deprecated with microsatellites)

## 1.2.2

BUG FIXES:

* rolebindings: fix overzealous whitespace removal in `if` directives

## 1.2.1

BUG FIXES:

* statsd-mapping configmap: fix outdated configmap name in deployment template

## 1.2.0

ENHANCEMENTS:

* lightstep/collector: update image to `2021-01-26_23-02-36Z`
* prom/statsd-exporter: update image to `v0.20.0`
* satellite config: Satellite GUID now defaults to pod name using Downward API
* service account: role, clusterRole, and corresponding bindings are now createable through the chart
* kubernetes secret and configmap names: resource names are now based on Helm release name to allow multiple installs without conflict or dependency on other install's resources
* securityContext: run user as nonroot with UID 1000

BUG FIXES:

* nodeSelector: deployment template properly renders if object defined for `nodeSelector`
* affinity: deployment template properly renders if object defined for `affinity`
* tolerations: deployment template properly renders if object defined for `tolerations`
* securityContext: remove `drop: ["ALL"]` for capabilities

BREAKING CHANGES:

* satellite secret: secret name now uses the helm release name
* statsd-mapping configmap: configmap name now uses the helm release name
* securityContext: run user as nonroot with UID 1000
