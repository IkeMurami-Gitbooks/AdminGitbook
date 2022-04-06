# Postfix (SMTP)

Нормальный мануал у digital ocean

## Другой пример

```
Ставим необходимые пакеты:
# yum -y install postfix cyrus-sasl-plain mailx


# Добавляем в /etc/postfix/canonical указание через какой аккаунт отправлять почту:
/.+/ noreply@example.com


Добавляем в /etc/postfix/mailpasswd логин и пароль релей-хостов:
[mx.example.com] SMTP_USER@example.com:SMTP_PASSWORD


Добавляем в /etc/postfix/sender_relay привязку доменов и конкретных отправителей к внешним службам:
@example.com [mx.example.com]

Добавляем блок в /etc/postfix/main.cf:
relayhost = [mx.example.com]
 
# Включение аутентификации на стороне клиента
smtp_sasl_auth_enable = yes
# Указывает на файл, в котором хранится база связок логин/пароль
smtp_sasl_password_maps = hash:/etc/postfix/mailpasswd
 
# Опции SASL. noanonymous указывает на запрет анонимной аутентификации
smtp_sasl_security_options = noanonymous
# Задает плагин SASL для аутентификации
smtp_sasl_type = cyrus
# Перечисляет механизмы проверки пользователя и пароля
smtp_sasl_mechanism_filter = login
 
# Включает зависящую от отправителя аутентификацию, отключает кэширование SMTP-соединения
smtp_sender_dependent_authentication = yes
# Указание на список адресов и почтовых серверов, через которые нужно отправлять письма на эти адреса
sender_dependent_relayhost_maps = hash:/etc/postfix/sender_relay
# Добавляет для домена указание через какой аккаунт отправлять почту
sender_canonical_maps = hash:/etc/postfix/canonical
 
# Добавляет отправку почты админу на внешний ящик
smtp_generic_maps = hash:/etc/postfix/generic
# Указывает, использовать ли TLS для SMTP
smtp_use_tls = yes

Редактируем параметр sendmail_path в /etc/php.ini:
sendmail_path = /usr/sbin/sendmail -t -i -f noreply@example.com

Генерируем индексированные файлы:
postmap /etc/postfix/generic
postmap /etc/postfix/canonical
postmap /etc/postfix/mailpasswd
postmap /etc/postfix/sender_relay

Добавляем в автозагрузку и запускаем сервис:
service php-fpm restart
systemctl enable postfix
systemctl start postfix
 
# проверка
echo "Test message" | mail -s "Test subject" -a "From: Test <noreply@example.com>" test@example.com

```
