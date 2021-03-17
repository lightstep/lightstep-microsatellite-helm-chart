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
