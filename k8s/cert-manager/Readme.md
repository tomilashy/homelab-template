

helm repo add jetstack https://charts.jetstack.io
helm repo update
kubectl create namespace cert-manager
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.11.0/cert-manager.crds.yaml
helm install cert-manager jetstack/cert-manager --namespace cert-manager --values=k8s/cert-manager/values.yml --version v1.11.0


* if you want issuer per namespace  use Issuer  instead of ClusterIssuer : https://cert-manager.io/docs/concepts/issuer/
