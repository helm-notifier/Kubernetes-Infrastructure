To get running fresh you need to install the two namespaces for openfaas via
`kubectl apply -f https://raw.githubusercontent.com/openfaas/faas-netes/master/namespaces.yml`
```
# generate a random password
PASSWORD=$(head -c 12 /dev/urandom | shasum| cut -d' ' -f1)

kubectl -n openfaas create secret generic basic-auth \
--from-literal=basic-auth-user=admin \
--from-literal=basic-auth-password="$PASSWORD"
```
Also need to add jetstack/cert-manager crds
```
kubectl apply \
    -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.8/deploy/manifests/00-crds.yaml
```
```
kubectl create namespace ingress-nginx
```# Kubernetes-Infrastructure
