# Docker Registry 


# Set up
## Password

```
source gen-registry-user-pass.sh <USERNAME> <PASSWORD>
kubectl apply -f namespace.yaml
kubectl create secret docker-registry reg-cred-secret --docker-server=registry.piwero.com --docker-username=myuser --docker-password=mypasswd
kubectl apply -f .
```

## Deploy with Helm 
`helm install test-registry charts/docker-registry/ --namespace test-registry --create-namespace`