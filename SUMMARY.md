# Table of contents

* [Admin Book](README.md)

## Network

* [Проблемы](network/problemy/README.md)
  * [Освободить порт](network/problemy/osvobodit-port.md)
* [Tools](network/tools/README.md)
  * [tshark](network/tools/tshark.md)
  * [Анализ трафика](network/tools/analiz-trafika.md)
  * [curl](network/tools/curl.md)
  * [nmap](network/tools/nmap.md)
  * [masscan](network/tools/masscan.md)
  * [ifconfig](network/tools/ifconfig.md)
  * [netcat/nc/socat](network/tools/netcat-nc.md)
  * [iptables](network/tools/iptables.md)
  * [netstat](network/tools/netstat.md)
  * [downloaders](network/tools/downloaders.md)
  * [openvpn3](network/tools/openvpn3.md)
  * [tcpdump](network/tools/tcpdump.md)
  * [databases](network/tools/databases/README.md)
    * [mysql](network/tools/databases/mysql.md)
    * [mssql](network/tools/databases/mssql.md)
  * [smbclient](network/tools/smbclient.md)
* [Протоколы](network/untitled/README.md)
  * [Почтовые протоколы](network/untitled/pochtovye-protokoly/README.md)
    * [pop3](network/untitled/pochtovye-protokoly/pop3.md)
    * [smtp](network/untitled/pochtovye-protokoly/smtp.md)
    * [imap](network/untitled/pochtovye-protokoly/imap.md)
    * [DMARC, SPF, DKIM](network/untitled/pochtovye-protokoly/dmarc-spf-dkim.md)
  * [TOR](network/untitled/tor.md)
  * [2G/3G/4G/5G](network/untitled/2g-3g-4g-5g.md)
  * [DNS](network/untitled/dns/README.md)
    * [Banner Grabbing](network/untitled/dns/banner-grabbing.md)
    * [rDNS (или PTR-записи)](network/untitled/dns/rdns.md)
    * [Zone Transfer](network/untitled/dns/zone-transfer.md)
    * [Купить свой домен](network/untitled/dns/kupit-svoi-domen.md)
  * [ssh](network/untitled/ssh.md)
  * [snmp](network/untitled/snmp.md)
  * [icmp](network/untitled/icmp.md)
  * [ldap](network/untitled/ldap.md)
  * [cisco](network/untitled/cisco.md)
* [Практические нюансы и подходы](network/prakticheskie-nyuansy-i-podkhody.md)

## Операционные системы

* [MacOS](operacionnye-sistemy/macos.md)
* [RedHat](operacionnye-sistemy/redhat.md)
* [Linux](operacionnye-sistemy/linux/README.md)
  * [Настройка Debian](operacionnye-sistemy/linux/nastroika-debian/README.md)
    * [Intro](operacionnye-sistemy/linux/nastroika-debian/intro.md)
    * [Oh My ZSH](operacionnye-sistemy/linux/nastroika-debian/oh-my-zsh.md)
    * [Установка графической оболочки](operacionnye-sistemy/linux/nastroika-debian/ustanovka-graficheskoi-obolochki.md)
    * [Firewall](operacionnye-sistemy/linux/nastroika-debian/firewall.md)
  * [Файловая система](operacionnye-sistemy/linux/failovaya-sistema/README.md)
    * [proc](operacionnye-sistemy/linux/failovaya-sistema/proc.md)
    * [Получить полный путь до файла](operacionnye-sistemy/linux/failovaya-sistema/poluchit-polnyi-put-do-faila.md)
    * [Размеры дисков, директорий, файлов](operacionnye-sistemy/linux/failovaya-sistema/razmery-diskov-direktorii-failov.md)
    * [Работа с дисками](operacionnye-sistemy/linux/failovaya-sistema/rabota-s-diskami.md)
    * [Работа с флешками и другими монтированными устройствами](operacionnye-sistemy/linux/failovaya-sistema/rabota-s-fleshkami-i-drugimi-montirovannymi-ustroistvami.md)
  * [Network](operacionnye-sistemy/linux/network.md)
  * [Security](operacionnye-sistemy/linux/security/README.md)
    * [namespaces & cgroups](operacionnye-sistemy/linux/security/namespaces-and-cgroups.md)
    * [SELinux](operacionnye-sistemy/linux/security/selinux.md)
    * [AppArmor](operacionnye-sistemy/linux/security/apparmor.md)
    * [eBPF](operacionnye-sistemy/linux/security/ebpf.md)
    * [audit.d](operacionnye-sistemy/linux/security/audit.d.md)
    * [Seccomp](operacionnye-sistemy/linux/security/seccomp.md)
  * [Background Services and Crons](operacionnye-sistemy/linux/background-services-and-crons.md)
  * [Troubleshooting](operacionnye-sistemy/linux/troubleshooting/README.md)
    * [Если нет звука](operacionnye-sistemy/linux/cases/net-zvuka.md)
  * [Cases](operacionnye-sistemy/linux/cases/README.md)
    * [nohup Поднять сервер без привязки к ssh-сессии](operacionnye-sistemy/linux/cases/nohup-podnyat-server-bez-privyazki-k-ssh-sessii.md)
    * [Отвязать процесс от родителя в bash](operacionnye-sistemy/linux/cases/otvyazat-process-ot-roditelya-v-bash.md)
    * [Нормальная консоль (возможность удаления данных, а не ^\[\[D)](operacionnye-sistemy/linux/cases/normalnaya-konsol-vozmozhnost-udaleniya-dannykh-a-ne-d.md)
    * [Установка пакетов](operacionnye-sistemy/linux/cases/ustanovka-paketov.md)
    * [Сетевые порты](operacionnye-sistemy/linux/cases/spisok-otkrytykh-portov.md)
    * [Установить переменную окружения глобально](operacionnye-sistemy/linux/cases/ustanovit-peremennuyu-okruzheniya-globalno.md)
    * [RDP Clients](operacionnye-sistemy/linux/cases/rdp.md)
  * [Команды](operacionnye-sistemy/linux/komandy/README.md)
    * [Список команд BusyBox](operacionnye-sistemy/linux/komandy/spisok-komand-busybox.md)
    * [source](operacionnye-sistemy/linux/komandy/source.md)
    * [grep](operacionnye-sistemy/linux/komandy/grep.md)
    * [ps](operacionnye-sistemy/linux/komandy/ps.md)
    * [find](operacionnye-sistemy/linux/komandy/find.md)
    * [vi](operacionnye-sistemy/linux/komandy/vi.md)
* [Windows](operacionnye-sistemy/windows/README.md)
  * [Packet Managers](operacionnye-sistemy/windows/packet-managers.md)
  * [Тулзы для администрирования](operacionnye-sistemy/windows/tulzy-dlya-administrirovaniya.md)
  * [Пути на системе](operacionnye-sistemy/windows/puti-na-sisteme.md)
  * [Работа с bat-никами](operacionnye-sistemy/windows/rabota-s-bat-nikami.md)
  * [ipconfig](operacionnye-sistemy/windows/ipconfig.md)
  * [Характеристики компа](operacionnye-sistemy/windows/kharakteristiki-kompa.md)
  * [Microsoft Store](operacionnye-sistemy/windows/microsoft-store.md)
  * [Образы Windows](operacionnye-sistemy/windows/obrazy-windows.md)
  * [cmd](operacionnye-sistemy/windows/cmd-1/README.md)
    * [reg](operacionnye-sistemy/windows/cmd-1/reg.md)
    * [sc](operacionnye-sistemy/windows/cmd-1/sc.md)
    * [net](operacionnye-sistemy/windows/cmd-1/net.md)
    * [Список разных команд (надо оформить в отдельные страницы)](operacionnye-sistemy/windows/cmd-1/cmd.md)
* [Tools](operacionnye-sistemy/tools/README.md)
  * [Файловый менеджер](operacionnye-sistemy/tools/failovyi-menedzher.md)
  * [Работа с архивами](operacionnye-sistemy/tools/rabota-s-arkhivami.md)
  * [Terminals](operacionnye-sistemy/tools/terminals.md)
  * [osquery](operacionnye-sistemy/tools/osquery.md)
  * [saltstack](operacionnye-sistemy/tools/saltstack.md)
  * [chef](operacionnye-sistemy/tools/chef.md)

## Tools

* [Развернуть свою виртуальную лабу на базе Windows](tools/razvernut-svoyu-virtualnuyu-labu-na-baze-windows.md)
* [Покупка доменов](tools/pokupka-domenov.md)
* [Настройка почты](tools/nastroika-pochty/README.md)
  * [Docker](tools/nastroika-pochty/docker.md)
  * [iRedMail](tools/nastroika-pochty/iredmail.md)
  * [Postfix (SMTP)](tools/nastroika-pochty/nastroika-postfix.md)
  * [Dovecot (IMAP)](tools/nastroika-pochty/dovecot-imap.md)
  * [Другие инструкции](tools/nastroika-pochty/drugie-instrukcii.md)
  * [fail2ban](tools/nastroika-pochty/fail2ban.md)
* [Splunk](tools/splunk.md)
* [Распределенные вычисления](tools/raspredelennye-vychisleniya/README.md)
  * [Apache Hadoop](tools/raspredelennye-vychisleniya/apache-hadoop.md)
  * [Уязвимости](tools/raspredelennye-vychisleniya/uyazvimosti.md)
* [Databases](tools/databases/README.md)
  * [клиенты](tools/databases/klienty.md)
  * [MongoDB](tools/databases/mongodb.md)
  * [postgres](tools/databases/postgres.md)
  * [mysql](tools/databases/mysql.md)
  * [H2 Database](tools/databases/h2-database.md)
  * [Experiments](tools/databases/experiments/README.md)
    * [neo4j](tools/databases/experiments/neo4j.md)
    * [edgedb](tools/databases/experiments/edgedb.md)
* [Servers](tools/servers/README.md)
  * [WEB](tools/servers/web/README.md)
    * [Apache](tools/servers/web/apache.md)
    * [Nginx](tools/servers/web/nginx.md)
    * [Oracle](tools/servers/web/oracle.md)
    * [IIS](tools/servers/web/iis.md)
    * [Passenger](tools/servers/web/passenger.md)
  * [one line servers](tools/servers/one-line-servers.md)
  * [Pi-hole: свой dns сервер](tools/servers/pi-hole-svoi-dns-server.md)
* [Удаленное управление серверами](tools/udalennoe-upravlenie-serverami/README.md)
  * [HP iLO](tools/udalennoe-upravlenie-serverami/hp-ilo.md)
* [VPN](tools/vpn/README.md)
  * [Pulse Secure SSL VPN](tools/vpn/pulse-secure-ssl-vpn.md)
  * [VPN WireGuard](tools/vpn/vpn-wireguard.md)
  * [OpenVPN](tools/vpn/openvpn.md)
* [CI/CD](tools/ci-cd/README.md)
  * [Gitlab CI](tools/ci-cd/gitlab-ci.md)
  * [TeamCity JetBrains](tools/ci-cd/teamcity-jetbrains.md)
  * [jenkins](tools/ci-cd/jenkins/README.md)
    * [Для чего](tools/ci-cd/jenkins/dlya-chego.md)
    * [Установка](tools/ci-cd/jenkins/ustanovka.md)
    * [Basic Usage](tools/ci-cd/jenkins/basic-usage.md)
    * [Pipelines](tools/ci-cd/jenkins/pipelines.md)
    * [Blue Ocean](tools/ci-cd/jenkins/blue-ocean.md)
    * [Security](tools/ci-cd/jenkins/security.md)
* [Визуализация/Отчетность/Работа с событиями](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/README.md)
  * [Allure](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/allure.md)
  * [Logstash](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/logstash.md)
  * [Kibana](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/kibana.md)
  * [Grafana](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/grafana.md)
  * [Elasticsearch](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/elasticsearch/README.md)
    * [Теория](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/elasticsearch/elasticsearch.md)
    * [Практика](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/elasticsearch/praktika.md)
  * [Kafka](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/kafka.md)
  * [Rsyslog](tools/vizualizaciya-otchetnost-rabota-s-sobytiyami/rsyslog.md)
* [RackTables](tools/racktables.md)
* [Мониторинг сети, приложений и событий](tools/monitoring-seti-prilozhenii-i-sobytii/README.md)
  * [Prometheus](tools/monitoring-seti-prilozhenii-i-sobytii/prometheus.md)
  * [Zabbix](tools/monitoring-seti-prilozhenii-i-sobytii/zabbix.md)
  * [snort](tools/monitoring-seti-prilozhenii-i-sobytii/snort.md)
  * [moloch](tools/monitoring-seti-prilozhenii-i-sobytii/moloch.md)

## Learning

* [Онлайн курсы](learning/onlain-kursy.md)
* [Подборки материалов](learning/podborki-materialov/README.md)
  * [DevOps](learning/podborki-materialov/devops.md)
  * [DevSecOps](learning/podborki-materialov/devsecops.md)
