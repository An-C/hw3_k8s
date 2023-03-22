

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
#### Создание Namespace (если отсутствует)
```
kubectl create namespace otus
```

###
### Установка приложения
```
helm install --namespace otus chart-user chart-user -f chart-user/values.yaml
```

###
#### Использование postman-коллекции
```
newman run "User Service.postman_collection.json"
```



#
#### Удаление приложения
```
helm delete chart-user -n otus
```






