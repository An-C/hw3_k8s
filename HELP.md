
###
#### Установка Ingress Controller-a (если не установлен)
```
kubectl create namespace m 
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update 
helm install nginx ingress-nginx/ingress-nginx --namespace m -f nginx-ingress.yaml
```

#### Дополнительные команды при неудачной установке чарта
```
kubectl delete job chart-user -n otus
kubectl delete pvc data-chart-user-postgresql-0 -n otus
```
