# install nginx ingress

```
helm install --name my-ingress stable/nginx-ingress \
  --set controller.kind=DaemonSet \
  --set controller.service.type=NodePort \
  --set controller.hostNetwork=true

NEW WAY
helm repo add nginx-stable https://helm.nginx.com/stable
helm repo update
kubectl create ns nginx-ingress
helm install --name my-ingress nginx-stable/nginx-ingress --set controller.kind=DaemonSet --set controller.service.type=NodePort --set controller.hostNetwork=true --namespace nginx-ingress
helm install --name my-ingress  nginx-stable/nginx-ingress  --namespace nginx-ingress --set controller.service.type=NodePort --set controller.hostNetwork=true
if the nginx does not start
kubectl edit deployments.apps my-ingress-nginx-ingress -n nginx-ingress
and change -enable-custom-resources flag to false
```

# start myapp

Create myapp and add an ingress rule:

```
kubectl create -f myapp.yml
kubectl create -f myapp-ingress.yml
```

# install cert-manager

```
helm install \
    --name cert-manager \
    --namespace kube-system \
    stable/cert-manager
```

```
OR
helm repo add jetstack https://charts.jetstack.io
helm repo update
helm install  --name cert-manager jetstack/cert-manager   --namespace cert-manager   --version v1.2.0      --set installCRDs=true
```

```
self-signed
k apply -f self-signed-issuer.yml
kubectl get issuers selfsigned-issuer -o wide
k apply -f certificate-self.yml
k apply -f  myapp-ingress-ssl-prebuild.yml
```
