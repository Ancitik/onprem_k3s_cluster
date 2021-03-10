# Mockserver

Mockserver is required to mock http requests to third-party services.

Deployeent is done through Helm v3 using the following command:

`kubectl create namespace mockserver`

`helm upgrade --install --namespace mockserver mockserver http://www.mock-server.com/mockserver-5.11.2.tgz -f values.yaml`

UI is available at https://mockserver.lab.local/mockserver/dashboard

And service can be reach at http://mockserver.mockserver.svc.cluster.local