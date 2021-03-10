# Longhorn

Longhorn create a storage cluster to create and provide PV and PVC to our kubernetes cluster.
It allows us to perform multi node deployments.

Longhorn is deployed through Helm within the Kubernetes cluster.

Deploying longhorn on K3S require a little tweaks to allow longhorn to find the right kubelet dir.

`helm install longhorn longhorn/longhorn --namespace longhorn-system --set csi.kubeletRootDir=/var/lib/kubelet`

Longhorn UI is avaibale through Rancher UI but if you don't need it you don't have to deploy rancher (It is not a rich-feature UI).