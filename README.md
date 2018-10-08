# Voraussetzungen
## Kubernetes
--> Ist in Docker for Desktop integriert

## Ingress
helm install --name ingress --namespace kube-system --set dashboard.enabled=true,dashboard.domain=traefik.lab stable/traefik

### Alternativ
https://istio.io/docs/setup/kubernetes/download-release/
helm install install/kubernetes/helm/istio --name istio --namespace istio-system

## Wildcard DNS
 *.lab --> 127.0.0.1

# Starten der aktuellen Imgages
kubectl create -f seite50.yaml

## Seite50
http://seite50.lab
http://seite50.lab/api

## Ingress Dashboard (Traefik)
http://traefik.lab/dashboard/


