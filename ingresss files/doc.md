# Install ingress

```bash
kubectl create namespace ingress-nginx
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm upgrade --install ingress-nginx ingress-nginx/ingress-nginx --namespace ingress-nginx --set controller.service.type=LoadBalancer --set controller.service.annotations."service\.beta\.kubernetes\.io/aws-load-balancer-type"=nlb
```