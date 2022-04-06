# docker cli part1

## Работа с Docker

[https://community.vscale.io/hc/ru/community/posts/211783625-Основы-работы-с-Docker](https://community.vscale.io/hc/ru/community/posts/211783625-%D0%9E%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81-Docker)

## Практические примеры использования docker

[https://blog.ropnop.com/docker-for-pentesters/](https://blog.ropnop.com/docker-for-pentesters/)

```
Запуск контейнера
docker run --rm -i -t --entrypoint=/bin/bash

docker run -d --name имя_контейнера имя_образа
    -d - запуск в автономном режиме
    --name - имя контейнера
    в конце - имя_образа

docker ps - запущенные контейнеры

docker rm -f имя_контейнера - удалить контейнер

docker run --name имя_контейнера -d -p 80:80 имя_образа
    Запуск нового контейнера с проброшенным портом (слева - порт сервиса, справа - через какой порт будут уходить сообщения)

Чтобы заменить какой-нибудь файл в контейнере, используется команда docker cp. Она копирует файл из локальной файловой системы в контейнер
docker cp qa_nginx:/etc/nginx/nginx.conf /tmp/nginx.conf
Где qa_nginx и /etc/nginx/nginx.conf - имя контейнера и путь к скачиваемому файлу из контейнера соответственно, а /tmp/nginx.conf путь до нового файла в текущей операционной системе.

Остановить контейнер 
docker stop qa_nginx
docker container prune - удалить все контейнеры, которые остановлены

docker image ls -> список установленных контейнеров
docker image rm <image_id> - удалить конт

Работа с терминалом
Отправка команды терминалу в контейнер
docker exec -it <container_id> <Команда>

-i - Оставить STDIN открытым, даже если контейнер запущен в неприкрепленном режиме
-t, -tty - Запустить псевдотерминал

Если мы удалим наш контейнер и вновь его запустим, то все наши изменения, сделанные через консоль, исчезнут. Чтобы сохранить изменения используется команда docker commit
 docker commit 2404abeecf66 nginx_mc
 Данная команда создаст новый образ nginx_mc, в котором будет уже установленный редактор mc. Здесь 2404abeecf66 - id контейнера, который можно узнать выполнив команду docker ps.


    Запускаем докер
    docker pull <repo> - загрузка репозитория
    docker run ... - запуск репозитория

docker load -i <some_image>.tar[.gz] - можно загружать образы из tar архивов (gz/gzip/tgz..)

 Подробная документация
 https://docs.docker.com/engine/reference/
```

## Безопасность Docker-контейнеров

Хороший материал об обеспечении безопасности Docker'а. Начиная от правильной конфигурации самого демона, и заканчивая настройкой seccomp (позволяет ограничить список системных вызовов, доступных конкретному приложению) и Docker secrets.

[https://0x00sec.org/t/securing-docker-containers/16913](https://0x00sec.org/t/securing-docker-containers/16913)
