Lightstep Satellite Helm Chart:

This is a helm chart used to deploy a Lightstep satellite.  All configuration should be made in the values.yaml file.  Nothing else should need to be modified.  This does not include metrics monitoring and the extra containers of the StatsD exporter or endpoints.

Required Configuration:

The minimum configuration for this to work is for the user to input either a Satellite API key or point to a kubernetes secret that contains the Satellite API key.


Running the helm chart:

In order to install the helm chart, clone the project, input your satellite key (and any other configuration desired) and then run  `helm install satellite /install/directory/satellite-helm-chart`