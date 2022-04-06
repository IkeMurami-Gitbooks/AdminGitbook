---
description: Примеры использования smbclient на linux
---

# smbclient

`smbmap` - можем узнать какие папки доступны\
Пример: `smbmap -u username -p 'password' -H 10.10.10.10 -P 139 (или 445) -p '0B186E661BBDBDCF6047784DE8B9FD8B:0B186E661BBDBDCF6047784DE8B9FD8B'`

* может использоваться NTLM-хеш. Причем, если установлено в настройках у SMB, что использовать только `sambaNTPassword`или `sambaLMPassword`, то вторая часть, может быть любой.

`smbclient`\
Узнать доступные папки\
`smbclient -W WORKGROUPS -U username -L 10.10.10.10`\
Подключиться к папке\
`smbclient -W WORKGROUPS -U username \\10.10.10.10\path2directory`\
Указать user и пароль:\
`smbclient -U 'username%password'`\
Передача файла\
`smbclient ... -c 'put myfile.txt'` - передаем файл с нашей машины на целевую
