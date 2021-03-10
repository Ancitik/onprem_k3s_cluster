# Harbor

Harbor is container and Helm charts repository with RBAC, Vulnerality scanner integration and high artifact signing with Notary.

It's used to store our Container images and enforce binary trust for clients.

It is currently the most complete open source solution of the market to deploy container registry on prem.

Here i deployed it using Helm v3 as following :

`helm install harbor --namespace harbor harbor/harbor -f values.yaml`

# Docker login troubleshoot

You might encounted issues trying to `docker login` cause certificates is selfsigned.

Personnaly, the problem came from Let's Encrypt was unable to issue a certificate due to DMZ's isolation.

A common workarround is to specify to the Docker daemon this repository as an unsecured one.

`sudo vi /etc/docker/daemon.json`

```
{
  "experimental": true,
  "insecure-registries": ["harbor.lab.local"]
}
```
Restart docker.

`sudo service docker restart`

