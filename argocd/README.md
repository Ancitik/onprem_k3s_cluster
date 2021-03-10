# ArgoCD

ArgoCD is responsible for syncing the state of a Kubernetes cluster with a Git repository where the cluster is declared.

It enforce a declarative model of our infrastruture which brings consistency and ease of maintenance.

It is deployed using a HelmChart CRD

`kubectl apply -f argocd.yaml`