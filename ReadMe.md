# TP Ingress

```zsh
kind create cluster --name my-cluster --config kind_config.yaml
```

```zsh
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
````

```zsh
kubectl wait --namespace ingress-nginx \
  --for=condition=ready pod \
  --selector=app.kubernetes.io/component=controller \
  --timeout=90s
```

## Voir le schéma dans le [fichier pdf](./TP%20Kubernetes%20Ingress.pdf)

Pour chaque dossier (Burger, Pizza et Tacos)
```zsh 
cd Burger/
docker build -t burger -f Dockerfile .
docker tag burger philippe1jonathan/restaurants:burger
docker push philippe1jonathan/restaurants:burger 
```

Voir le fichier [ingress.yaml](./ingress.yaml) et les fichiers "conf.yaml" dans chaque dossier :
Burger : [conf.yaml](./Burger/conf.yaml) / Pizza : [conf.yaml](./Pizza/conf.yaml) / Tacos : [conf.yaml](./Tacos/conf.yaml)

