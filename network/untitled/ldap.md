---
description: LDAP - клиент-серверный протокол для доступа к службе каталогов.
---

# ldap

`Root DSE` - Концептуально — запись самого верхнего уровня в иерархии `LDAP`, можно сказать `super root` (супер-корневая запись). Обычно невидима, то есть к ней нельзя получить доступ с помощью нормальных операций. Иногда её путают с `root` (корневой записью), она же `base` (базовая запись), она же `suffix` (суффикс). `DSE` расшифровывается как `DSA Specific Entry` (специфичная для `DSA` запись), в свою очередь `DSA` расшифровывается как `Directory System Agent` (системный агент каталога, то есть любая служба каталогов, предоставляющая доступ через `DAP` или `LDAP`). Информация по `rootDSE` в `OpenLDAP` может быть получена путём запроса объектного класса `OpenLDAProotDSE` или, в любом `LDAP`-сервере (включая `OpenLDAP`), путём запроса установки анонимного подсоединения с пустым базовым `DN` (`""`). Эта информация будет содержать данные о поддерживаемых версиях протокола, сервисах и контекстах именования (`DIT`).

```
В nmap:

$ > locate -r nse$|grep ldap
$ > nmap -p 389 --script ldap-rootdse -Pn 10.10.10.107

PORT STATE SERVICE
389/tcp open ldap
| ldap-rootdse:
| LDAP Results
| <ROOT>
| supportedLDAPVersion: 3
| namingContexts: dc=hackthebox,dc=htb
| supportedExtension: 1.3.6.1.4.1.1466.20037
|_ subschemaSubentry: cn=schema

Получаем два namingContexts: hackthebox, htb - т.е. это два пространства имен (?)

Эту информацию будем использовать для поиска по ldap (ldap-search):
$ > locate -r nse$|grep ldap
$ > nmap -p 389 --script ldap-search -Pn 10.10.10.107
dn - каталог (уникальная запись, состоящая из rdn - relative dn)
Подробнее об этом см. : https://pro-ldap.ru/tr/zytrax/apa/dn-rdn.html
```

Понятия в ldap: [https://pro-ldap.ru/tr/zytrax/apd/](https://pro-ldap.ru/tr/zytrax/apd/)
