# Voraussetzungen
1. Kubernetes
--> Ist in Docker for Desktop integriert

2. Kubernetes Nginx-Ingress Controller (https://github.com/kubernetes/ingress-nginx)
--> geht mit Hel: helm install stable/nginx-ingress --name ingress-nginx --namespace ingress-nginx --set controller.extraArgs.enable-ssl-passthrough=""

3. Hosts Eintrag
127.0.0.1 seite50.lab

# Starten der aktuellen Imgages
kubectl create -f seite50.yaml
