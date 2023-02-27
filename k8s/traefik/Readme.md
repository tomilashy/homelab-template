helm repo add traefik https://traefik.github.io/charts
helm repo update
kubectl create namespace traefik


full values can be see by:
helm show values traefik/traefik > values.yml or can be gotten from https://github.com/traefik/traefik-helm-chart/blob/master/traefik/values.yaml


helm install --namespace=traefik traefik/traefik -f  ~/k8s/traefik-values.yml
<!-- # kubectl apply --server-side --force-conflicts -k https://github.com/traefik/traefik-helm-chart/traefik/crds/ -->

helm upgrade traefik traefik/traefik -f traefik/values.yml -n traefik