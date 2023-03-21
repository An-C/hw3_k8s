

 Домашнее задание
## Инфраструктурные паттерны

### Описание/Пошаговая инструкция выполнения домашнего задания:
- Сделать простейший RESTful CRUD по созданию, удалению, просмотру и обновлению пользователей.
Пример API - https://app.swaggerhub.com/apis/otus55/users/1.0.0
- Добавить базу данных для приложения.
- Конфигурация приложения должна хранится в Configmaps.
- Доступы к БД должны храниться в Secrets.
- Первоначальные миграции должны быть оформлены в качестве Job, если это требуется.
- Ingress-ы должны также вести на url arch.homework



###
#### Namespace (если отсутствует)
```
kubectl create namespace m 
```

###
#### Установка Ingress Controller-a (если не установлен)
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update 
helm install nginx ingress-nginx/ingress-nginx --namespace m -f nginx-ingress.yaml
```
###
#### Установка БД (если не установлена)
```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install --namespace m user-db bitnami/postgresql -f pg-values.yaml
```
###
### Установка приложения
```
helm install --namespace m chart-user chart-user -f chart-user/values.yaml
```

###
#### Использование postman-коллекции
- импортировать коллекцию User Service.postman_collection.json
- в baseUrl должно быть прописано значение http://arch.homework



#
#### Удаление приложения и БД
```
helm delete chart-user -n m
helm delete user-db -n m
```


#### Дополнительные команды при неудачной установке чарта
```
kubectl delete job chart-user
kubectl delete pvc data-user-db-postgresql-0
```




