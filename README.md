# Voraussetzungen
## Kubernetes
--> Ist in Docker for Desktop integriert

## Seite50

kubectl apply -f seite50.yaml

## Ingress mit Traefik
helm install --name ingress --namespace kube-system --set dashboard.enabled=true,dashboard.domain=traefik.lab stable/traefik
kubectl create -f seite50-traefik.yaml
### Ingress Dashboard (Traefik)
http://traefik.lab/dashboard/

## Ingress mit Istio
https://github.com/istio/istio/tree/master/install/kubernetes/helm/istio
Eventuell kubectl delete -f install/kubernetes/helm/istio/templates/crds.yaml falls istio schonmal installiert war

helm install install/kubernetes/helm/istio --name istio --namespace istio-system --set sidecarInjectorWebhook.enabled=true --set servicegraph.enabled=true --set tracing.enabled=true --set ingress.enabled=false --set gateways.istio-ingressgateway.enabled=false --set gateways.istio-egressgateway.enabled=false --set kiali.enabled=true --set kiali.dashboard.passphrase=admin

kubectl create -f seite50-istio.yaml

### Kiali Dashboard
kubectl create -f istio.yaml
http://kiali.lab


## Wildcard DNS
 *.lab --> 127.0.0.1

## Seite50
http://seite50.lab
http://seite50.lab/api




