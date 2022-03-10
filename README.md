# helm-charts
# Installation Steps
helm repo add helm-charts https://rezoruno.github.io/helm-charts
helm install $name helm-charts/nginx -n $namespace

Get the application URL by running these commands:
export NODE_PORT=$(kubectl get --namespace $namespace -o jsonpath="{.spec.ports[0].nodePort}" services $service)
export NODE_IP=$(kubectl get nodes --namespace $namespace -o jsonpath="{.items[0].status.addresses[0].address}")
echo http://$NODE_IP:$NODE_PORT
