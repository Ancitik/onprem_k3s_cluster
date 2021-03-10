# Nexus

Nexus is used to store project dependencies and release of developped application before containerization or delivery.

Nexus is deploy using Helm as folllwing :

`helm install sonatype-nexus oteemocharts/sonatype-nexus --namespace nexus -f nexus/values.yaml`