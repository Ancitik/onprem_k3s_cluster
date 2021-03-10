# Traefik

Traefik was install by default in K3S but the version was 1.7.

Since Traefik provided further integration with Kubernetes I decided to redeploy K3S without Traefik using `--disable traefik` during it's installation.

Treaefik 2.3 is used as on ingress controller using standard Kubernetes Ingress object or Trafik IngressRoute CRD.

While deploying applications using Helm chart, since most of Helm charts maintainer provide Ingress integration, I choosed to use annotations withing charts `values.yaml` to tell Kube API to traefik as the Ingress Controller.

To do this I use these annotations :

    certmanager.k8s.io/acme-challenge-type: "http01"
    cert-manager.io/cluster-issuer: "letsencrypt-staging"
    kubernetes.io/ingress.class: "traefik"

Here I tell the Kube api to use traefik ingress controller and cert-manager to provide a certificate for this entry using the `letsencrypt-staging` issuer using http challenge to avoid bans from Let's Encrypt since I do multiple operations.

As mentioned during the last daily meeting, we must use dns challenge instead since port 80 is closed.

Examples are available in `../rancher` or `../nexus`.

Overwise, while deploying applications using classic manifests, I decided to use Trarfik IngressRoute.
It provide more readable and maintainable object to expose our services.

An example is `./dashboard.yaml`


Traefik is deployed using HelmChart CRD.

`kubectl apply -f traefik.yaml`

Then wait for Traefik to be deployed. And deploy the dashboard using IngressRoute

`kubectl apply -f dashboard.yaml`