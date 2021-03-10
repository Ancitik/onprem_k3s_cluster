# [WIP] Deployment manifests

Here I mostly choosed to used the Helm CRDs provided by Rancher.

If you are not running on K3s, you will need to install https://github.com/k3s-io/helm-controller

It enables us to install/upgrade/remove application through Helm charts.
Helm is launch within the cluster rather than on the developper workstation. It's a conception choice made to add consistancy to the cluster lifecycle in a self-control philosophy

Deploying a HelmChart object on the cluster result in an automated installation of the application.

With some templating using Kustomize we could easily template values in manifests.
I did not had enough time to do so.

Some application use standard Helm deployment using the values.yaml file but it will evolve.