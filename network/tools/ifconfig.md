# ifconfig

ifconfig interface ...

Описание вывода:\
MTU (Maximum transmission unit) - объем информации в одном пакете без учета заголовка\
inet - сетевой (IP) адрес сетевого интерфейса\
netmask - маска сети\
destination\
inet6 - сетевой (IPv6) адрес сетевого интерфейса\
prefixlen\
scopeid

```
ifconfig -a - выводим все интерейсы
ifconfig interface - инфа по одному интерфейсу
ifconfig interface [ip] - установить IP-адрес
ifconfig interface [-]promisc - перевести в promiscuous mode - прослушивающий режим
```
