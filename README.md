# Voraussetzungen
## Kubernetes
--> Ist in Docker for Desktop integriert

## Ingress mit Traefik
helm install --name ingress --namespace kube-system --set dashboard.enabled=true,dashboard.domain=traefik.lab stable/traefik
kubectl create -f seite50-traefik.yaml
### Ingress Dashboard (Traefik)
http://traefik.lab/dashboard/

## Ingress mit Istio
https://github.com/istio/istio/tree/master/install/kubernetes/helm/istio
helm install install/kubernetes/helm/istio --name istio --namespace istio-system --set sidecarInjectorWebhook.enabled=true --set servicegraph.enabled=true --set tracing.enabled=true --set ingress.enabled=false --set gateways.istio-ingressgateway.enabled=false --set gateways.istio-egressgateway.enabled=false --set kiali.enabled=true

kubectl create -f seite50-istio.yaml

### Kiali Dashboard
kubectl create -f istio.yaml
http://kiali.lab


## Wildcard DNS
 *.lab --> 127.0.0.1

## Seite50
http://seite50.lab
http://seite50.lab/api




