# ssh

## Информация по настройке openssh

Папка сервиса ssh находится в `/etc/ssh, sshd_config` - файл для настройки ssh-сервера\
После каждого изменения нужно перезапускать ssh-сервер:\
`sudo service ssh stop | start | restart`

Авторизация по паролю: `PasswordAuthentication no`\
Запретить пустой пароль: `PermitEmptyPasswords no`\
Авторизация по публичному ключу: `PubkeyAuthentication yes`

Указать путь до ключей:\
Для помещения ключей в папке пользователей: `AuthorizedKeysFile %h/.ssh/my_keys`\
Для помещения ключей всех в одном файле: `AuthorizedKeysFile /etc/ssh/authorized_keys`

На клиенте\
Генерация ключа\
`ssh-keygen -t ed25519`\
`putty -i private_key -ssh [user]@[ip]`

Информация по поддерживаемым алгоритмам SSH:\
`ssh -vvv -p <port <host>`

`sshpass` - утилита для подключения к удаленным серверам по SSH. Часто применяется в скриптах.\
brew install [https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb](https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb)
