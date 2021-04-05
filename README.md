# Lightstep Microsatellite Helm Chart

This is a Helm chart used to deploy a Lightstep **microsatellite**. This repo is a fork of [lightstep-satellite-helm-chart](https://github.com/lightstep/lightstep-satellite-helm-chart/) for Lightstep microsatellites. Everything version 2.0.0 and after will be for microsatellites only.

All configuration should be made in the `values.yaml` file. Nothing else should need to be modified. This does not include metrics monitoring and the extra containers of the StatsD exporter or endpoints.

## Required Configuration:

The minimum configuration for this to work is for the user to input either a Satellite API key or point to a kubernetes secret that contains the Satellite key.

If you're using an existing secret, enter the name and key of the secret that stores your satellite key.  The values.yaml requires values for the secret name and secret key value, as below:

```
$ kubectl describe secret ${collector_satellite_key_secret_name}

Name:         collector_satellite_key_secret_name

Namespace:    default

Labels:       <none>

Annotations:  <none>

Type:  Opaque

Data

collector_satellite_key_secret_key:  390 bytes
```

## Running the helm chart:

In order to install the helm chart, clone the project, input your satellite key (and any other configuration desired) and then run

```
helm install satellite lightstep-microsatellite-helm-chart
```

Or match the file path to the directory you installed.

Or install the helm chart from artifact hub here: https://artifacthub.io/packages/helm/lightstep-microsat/lightstep

# Contributors

Please delete the `charts/microsatellite/README.md` and regenerate it with the [helm-docs](https://github.com/norwoodj/helm-docs) command.
