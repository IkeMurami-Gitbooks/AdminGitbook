# Список разных команд (надо оформить в отдельные страницы)

more < file.txt - вывести файл в консоль

**reg** - программа для работы с реестром. Позволяет искать и изменять реестр

ftp - работа с ftp серверами

cmdkey /list - список сохраненных кредов пользователей

**icacls** /directory - посмотреть права различных пользователей на директрию

Запустить команду от другого пользователя:\
**runas** /user:domain\username "cmd /C more < test.txt > out.txt" /savecred - использовать сохраненные креды (см. cmdkey /list)

**whoami** - текущий пользователь системы

**net user** - пользователи в системе

**netsh** **firewall** show state - работа с web firewall\
Про troubleshooting проблем с настройкой сети (в тч и icmp echo enable): [https://docs.microsoft.com/en-us/troubleshoot/windows-server/networking/netsh-advfirewall-firewall-control-firewall-behavior#command-example-4-configure-icmp-settings](https://docs.microsoft.com/en-us/troubleshoot/windows-server/networking/netsh-advfirewall-firewall-control-firewall-behavior#command-example-4-configure-icmp-settings)
