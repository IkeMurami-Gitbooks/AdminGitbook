# iRedMail

Скачиваем tar.gz-архив

Добавляем в /etc/hosts домен будущего почтового сервера (запись mx и соотв домен уже настроили)

```
configure a fully qualified domain name (FQDN) in /etc/hosts before we go further.

Example:

127.0.0.1   mail.iredmail.org mail localhost
```

```
# cd /root
# tar -xf iRedMail-*
# cd iRedMail-*
# bash iRedMail.sh
```

Далее,&#x20;

user admin — postmaster@example.com

Админка будет доступна по линку: https://example.com/iredadmin/

WEB-клиент: https://example.com/mail/



Ну а далее открываем нужные порты и готово)
