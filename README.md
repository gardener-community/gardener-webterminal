# gardener-webterminal
These Helmcharts help to deploy the gardener-webterminal feature.
They consist of two charts:
1. terminal-controller-manager-**application**:
    Has to be deployed to the **virtual-garden-cluster**
3. terminal-controller-manager-**runtime**:
    Has to be deployed to the **garden-cluster**
    
### Values
Make sure that both ```values.yaml``` files contain the same certificate.
You have the possibility to generate the necessary certificate via the certmanager. Enabled it in the values.yaml at ```.Values.certificate.certManager.enabled```

### Installation
If you are using HelmReleases to deploy the Helmcharts use the examples in ```examples/```.

### Additional Edits
You have to enable the webterminal feature also in the gardener-dashboard values and set some additional values. See ```examples/dashboard-values.yaml```.

Also, the gardenlet values should contain ```.global.gardenlet.config.seedConfig.spec.secretRef``` and ```.global.gardenlet.config.seedConfig.spec.dns```
