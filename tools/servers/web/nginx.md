# Nginx

может проксировать не только http, но и tcp/udp/ssh.. трафик

Настройка по кнопочкам: проект NginxConfig — [https://do.nginxconfig.io/](https://do.nginxconfig.io/)

Path Traversal in misconfig aliases: [https://www.acunetix.com/vulnerabilities/web/path-traversal-via-misconfigured-nginx-alias/](https://www.acunetix.com/vulnerabilities/web/path-traversal-via-misconfigured-nginx-alias/)

## Сжатие

* gzip + brotli

## Поддержка HTTP/2

Позволяет прогружать контент в кучу потоков (для HTTP/1.1 браузер ограничивает количество потоков)

## Preload and HTTP/2 Push

Preload — подгружает файлы статики еще в момент загрузки заголовков (как то подсовывает)

HTTP/2 Push (объявлено deprecated, но еще поддерживаются)

## Проксирование трафика на другой сервис или контейнер

```
somedir/
    nginx/
        certs/  — это серт для TLS (может быть любой вообще, лишь бы был)
            cert.crt
            cert.key
            domain.csr  
        nginx.conf
    stunnel/  — proxy-server для построения туннеля (может быть любой сервис, например flask)
        certs/
            ...
        Dockerfile
        stunnel.txt
    docker-compose.yml
```

nginx.conf: по факту говорим, что в зависимости от Host-заговка трафик будет перенаправлен либо на http либо на stunnel (в этом примере)

```
server {
    listen 443 ssl;
    server_name  example.com;
    ssl_certificate /etc/nginx/certs/cert.crt;
    ssl_certificate_key /etc/nginx/certs/cert.key;    
    location / {
        proxy_pass http://example.com:80/;
        error_log /var/log/front_end_errors.log;
    }
}

server {
    listen 443 ssl;
    server_name  evil.com;
    ssl_certificate /etc/nginx/certs/cert.crt;
    ssl_certificate_key /etc/nginx/certs/cert.key;    
    location / {
        proxy_pass http://evil.com:80/;
        error_log /var/log/front_end_errors.log;
    }
}

server {
    listen 443 ssl;
    server_name  somesite.com;
    ssl_certificate /etc/nginx/certs/cert.crt;
    ssl_certificate_key /etc/nginx/certs/cert.key;    
    location / {
        proxy_pass http://stunnel:5555/;
        proxy_set_header Host somesite.com;
        error_log /var/log/front_end_errors.log;
    }
}
```

docker-compose.yml:

```
version: "3"
services:
  nginx:
    image: nginx
    ports:
      - "443:443"
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/conf.d/default.conf
      - ./nginx/certs:/etc/nginx/certs

  stunnel:
    build: stunnel
    dns:
      - 8.8.8.8



```
