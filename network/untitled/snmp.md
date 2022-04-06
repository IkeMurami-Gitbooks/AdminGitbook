# snmp

`SNMP` — `Simple Network Management Protocol` — простой протокол сетевого управления. Стандартный интернет-протокол для управления устройствами в `IP`-сетях на основе архитектур `TCP/UDP`. К поддерживающим `SNMP` устройствам относятся маршрутизаторы, коммутаторы, серверы, рабочие станции, принтеры, модемные стойки и другие. Протокол обычно используется в системах сетевого управления для контроля подключённых к сети устройств на предмет условий, которые требуют внимания администратора. `SNMP` определён Инженерным советом интернета (`IETF`) как компонент `TCP/IP`. Он состоит из набора стандартов для сетевого управления, включая протокол прикладного уровня, схему баз данных и набор объектов данных.

```bash
Find: $ nmap -sU --open -p 161 <IPs> -oA nmap/carrier_SNMP

Enum: $ snmpwalk -c <community> -v[1|2c|3] <IP> [group]
community - строка, например: public (чаще всего), private, manager,..
-v - версия протокола 1, 2с или 3
group - это часть дерева, которое ищем
Примеры:
Enum MIB Tree: $ snmpwalk -c public -v1 192.168.1.100
Пример ответа:
iso.3.6.1.2.1.47.1.1.1.1.11 = STRING: "SN#NET_45JDX23"
End of MIB

Enum Windows Users: $ snmpwalk -c public -v1 <IP> 1.3.6.1.4.1.77.1.2.25
Enum Running Win Process: $ ... 1.3.6.1.2.1.25.4.2.1.2
Enum Open TCP-ports: $ ... 1.3.6.1.2.1.6.13.1.3
Enum Installing Software: $ ... 1.3.6.1.2.1.25.6.3.1.2
```

```
OIDs MS Windows:
System Processes - 1.3.6.1.2.1.25.1.6.0
Running Programs - 1.3.6.1.2.1.25.4.2.1.2
Processes Path - 1.3.6.1.2.1.25.4.2.1.4
Storage Units - 1.3.6.1.2.1.25.2.3.1.4
Software Name - 1.3.6.1.2.1.25.6.3.1.2
User Accounts - 1.3.6.1.4.1.77.1.2.25
TCP Local Ports - 1.3.6.1.2.1.6.13.1.3
```



## Tools

### snmpwalk, snmp-check

snmpwalk и snmp-check - тулзы для работы с SNMP

ex\
snmpwalk -c \<comunity name, ex: public> -v1 \<ip> \[\<OID>]

### onesixtyone&#x20;

enum community names

```
root@kali:~# echo public > community
root@kali:~# echo private >> community
root@kali:~# echo manager >> community
root@kali:~# for ip in $(seq 1 254);do echo 10.11.1.$ip;done > ips 
root@kali:~# onesixtyone -c community -i ips
```

