# smtp

[https://www.samlogic.net/articles/smtp-commands-reference.htm](https://www.samlogic.net/articles/smtp-commands-reference.htm)

```
telnet <ip> 25

    Первая команда всегда HELO (или EHLO - Для Extended SMTP - ESMTP): HELO test
    QUIT - выход

В ESMTP:
3. AUTH

Пример сессии ESMTP:
EHLO test
AUTH LOGIN
334 VXNlcm5hbWU6
login
334 UGFzc3dvcmQ6
password
QUIT
```

## User Enum

VRFY username - можно производить enum пользователей

Через команду RCPT TO: смотреть на разницу в ответе

```
MAIL FROM: test@example.com
RCPT TO: hr@victim.com
```

## Клиенты

Для отправки сообщений можно использовать postfix

[MailHog](https://github.com/mailhog/MailHog) — Go smtp server с WEB UI интерфейсом. Позволяет удобно отлаживать и просматривать те сообщения, что отправляет ваше приложение.&#x20;
