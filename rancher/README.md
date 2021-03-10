# Rancher

Rancher provide cluster governance and visialisation.
I didn't used it really much since I prefred command line interfaces but it can be a good choice for developpers.

Rancher is deploy using Helm as folllwing :

`helm install rancher rancher-stable/rancher \
  --namespace cattle-system \
  -f rancher/values.yaml`
