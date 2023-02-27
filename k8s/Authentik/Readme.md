helm repo add authentik https://charts.goauthentik.io
helm repo update
default values - https://artifacthub.io/packages/helm/goauthentik/authentik#values

kubectl apply -f ~/k8s/authentik/persistentvolume.yml 
helm install --namespace=authentik authentik authentik/authentik --values=authentik/values.yml

# UPGRADE
helm upgrade --install --namespace=authentik authentik authentik/authentik -f authentik/values.yml 
# UNINSTALL
helm uninstall authentik -n authentik
kubectl delete all,pvc --all -n authentik
kubectl delete -f ~/k8s/authentik/persistentvolume.yml 
kubectl get ingress,certificate,svc,pv,pvc,all -n authentik
# TEMPLATE
helm template authentik/authentik -f authentik/values.yml > authentik/temp.yml

After installation
https://www.youtube.com/watch?v=Nh1qiqCYDt4&t