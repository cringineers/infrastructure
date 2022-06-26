# Цифровой прорыв. Репозитории комады Default:
- [Репозиторий - фронтенд](https://github.com/cringineers/tagger_frontend)
- [Репозиторий - api](https://github.com/cringineers/api)
- [Репозиторий - auth](https://github.com/cringineers/auth_api)
- [Репозиторий - worker нейронной сети](https://github.com/cringineers/worker)
- [Репозиторий - репозиторий с инфраструктурой](https://github.com/cringineers/infrastructure)
- [Репозиторий - предсказание нейронной сети, подсчет метрик](https://github.com/cringineers/model)

# Infrastructure
В данном репозитории содержатся все манифесты и конфигурационные файлы, необходимые для развёртывания в Kubernetes-кластере и запуска в dev-окружении.
- `api-server` - [api-сервер](https://github.com/cringineers/api)
- `auth-server` - [auth-сервер](https://github.com/cringineers/auth_api)
- `worker` - [worker-сервер](https://github.com/cringineers/worker)
- `web-ui` - [tagger-frontend](https://github.com/cringineers/tagger_frontend)
- `compose` - dev-окружение в Docker-compose
- `ingress` - настройки NGINX Ingress
- `common` - общие параметры (секреты, конфиги и т.п.)
- `minio` - values для запуска minio из helm-чарта

Для настройки кластера необходимо:
1. "подтянуть" секреты (из внешнего безопасного хранилища или заполнить рукми и сделать `kubectl apply`)
  1. В первую очередь - `common`
2. Запустить инстансы СУБД и Minio
3. Для каждого из компонентов системы сделать `kubectl apply -f deployment.yaml,service.yaml`
4. Добавить ingress (нужно заменить хосты на нужные)
