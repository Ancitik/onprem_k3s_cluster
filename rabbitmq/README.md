# RabbitMQ

A RabbitMQ cluster is created using the RabbitMQ Operator.

First install the operator running the following

`kubectl apply -f "https://github.com/rabbitmq/cluster-operator/releases/latest/download/cluster-operator.yml"`

Then create the cluster.

`kubectl apply -f rabbit-cluster.yaml`

Notes: RabbitMQ Cluster Kubernetes Operator currently does not support the ExternalName Service Type. Create a Traefik IngressRoute if you want to access the UI.