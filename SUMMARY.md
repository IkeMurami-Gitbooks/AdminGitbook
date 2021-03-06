# Table of contents

* [Admin Book](README.md)

## Песочницы, контейнеры, виртуализация <a href="#pesochnicy-konteinery" id="pesochnicy-konteinery"></a>

* [Какие есть](pesochnicy-konteinery/kakie-est.md)
* [Kubernetes](pesochnicy-konteinery/kubernetes/README.md)
  * [Tools](pesochnicy-konteinery/kubernetes/tools.md)
  * [Компоненты](pesochnicy-konteinery/kubernetes/komponenty.md)
  * [Термины](pesochnicy-konteinery/kubernetes/terminy.md)
  * [kubectl](pesochnicy-konteinery/kubernetes/kubectl.md)
  * [minikube](pesochnicy-konteinery/kubernetes/minikube.md)
  * [tiller](pesochnicy-konteinery/kubernetes/tiller.md)
  * [helm](pesochnicy-konteinery/kubernetes/helm.md)
  * [security](pesochnicy-konteinery/kubernetes/security.md)
  * [Learn](pesochnicy-konteinery/kubernetes/learn.md)
* [Container Runtime Interface (CRI)](pesochnicy-konteinery/container-runtime-interface-cri/README.md)
  * [containerd](pesochnicy-konteinery/container-runtime-interface-cri/containerd.md)
  * [CRI-O](pesochnicy-konteinery/container-runtime-interface-cri/cri-o.md)
  * [Docker](pesochnicy-konteinery/container-runtime-interface-cri/docker/README.md)
    * [About](pesochnicy-konteinery/container-runtime-interface-cri/docker/about.md)
    * [CLI](pesochnicy-konteinery/container-runtime-interface-cri/docker/cli/README.md)
      * [docker cli part1](pesochnicy-konteinery/container-runtime-interface-cri/docker/cli/docker-cli-part1.md)
      * [docker cli part2](pesochnicy-konteinery/container-runtime-interface-cri/docker/cli/docker.md)
    * [docker-compose](pesochnicy-konteinery/container-runtime-interface-cri/docker/docker-compose.md)
    * [Dockerfile](pesochnicy-konteinery/container-runtime-interface-cri/docker/dockerfile/README.md)
      * [Написание своего конфига](pesochnicy-konteinery/container-runtime-interface-cri/docker/dockerfile/dockerfile.md)
      * [My Examples](pesochnicy-konteinery/container-runtime-interface-cri/docker/dockerfile/my-examples.md)
    * [registry](pesochnicy-konteinery/container-runtime-interface-cri/docker/registry.md)
    * [\[Def\] Security](pesochnicy-konteinery/container-runtime-interface-cri/docker/def-security.md)
    * [\[Off\] Security](pesochnicy-konteinery/container-runtime-interface-cri/docker/ataki.md)
* [Red Hat OpenShift Container Platform (OCP)](pesochnicy-konteinery/openshift/README.md)
  * [About](pesochnicy-konteinery/openshift/about.md)
  * [OCP Components](pesochnicy-konteinery/openshift/ocp-components/README.md)
    * [Platform services](pesochnicy-konteinery/openshift/ocp-components/platform-services.md)
    * [Application services](pesochnicy-konteinery/openshift/ocp-components/application-services.md)
    * [Developer services](pesochnicy-konteinery/openshift/ocp-components/developer-services.md)
    * [OpenShift Kubernetes Engine](pesochnicy-konteinery/openshift/ocp-components/openshift-kubernetes-engine.md)
  * [Security](pesochnicy-konteinery/openshift/security/README.md)
    * [Container Security](pesochnicy-konteinery/openshift/security/container-security.md)
    * [Podman](pesochnicy-konteinery/openshift/security/podman.md)
    * [Kubernetes Security](pesochnicy-konteinery/openshift/security/kubernetes-security.md)
    * [Securing Platform Services](pesochnicy-konteinery/openshift/security/securing-platform-services.md)
    * [Vulnerabilities](pesochnicy-konteinery/openshift/security/vulnerabilities.md)
    * [CIS](pesochnicy-konteinery/openshift/security/cis.md)
* [VMWare](pesochnicy-konteinery/vmware/README.md)
  * [Workspace ONE Access](pesochnicy-konteinery/vmware/workspace-one-access.md)
  * [Workspace One UEM SSRF (AirWatch)](pesochnicy-konteinery/vmware/workspace-one-uem-ssrf-airwatch.md)
  * [vSphere](pesochnicy-konteinery/vmware/vsphere.md)
  * [vCenter](pesochnicy-konteinery/vmware/vcenter.md)
  * [Learn](pesochnicy-konteinery/vmware/learn.md)
  * [Horizon Security Server](pesochnicy-konteinery/vmware/horizon-security-server.md)
  * [VMWare log4j](pesochnicy-konteinery/vmware/vmware-log4j.md)
* [Tools](pesochnicy-konteinery/tools/README.md)
  * [Moby](pesochnicy-konteinery/tools/moby.md)
  * [Security](pesochnicy-konteinery/tools/security.md)

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
    * [Отвязать процесс от родителя в bash](operacionnye-sistemy/linux/cases/otvyazat-process-ot-roditelya-v-bash.md)
    * [Нормальная консоль (возможность удаления данных, а не ^\[\[D)](operacionnye-sistemy/linux/cases/normalnaya-konsol-vozmozhnost-udaleniya-dannykh-a-ne-d.md)
    * [Установка пакетов](operacionnye-sistemy/linux/cases/ustanovka-paketov.md)
    * [Список открытых портов](operacionnye-sistemy/linux/cases/spisok-otkrytykh-portov.md)
    * [Установить переменную окружения глобально](operacionnye-sistemy/linux/cases/ustanovit-peremennuyu-okruzheniya-globalno.md)
    * [RDP Clients](operacionnye-sistemy/linux/cases/rdp.md)
  * [Команды](operacionnye-sistemy/linux/komandy/README.md)
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

## Tools

* [git](tools/untitled.md)
* [Развернуть свою виртуальную лабу на базе Windows](tools/razvernut-svoyu-virtualnuyu-labu-na-baze-windows.md)
* [Свой веб-сайт бесплатно](tools/svoi-veb-sait-besplatno.md)
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
* [Управление конфигурациями](tools/upravlenie-konfiguraciyami/README.md)
  * [Способы писать конфигурации](tools/upravlenie-konfiguraciyami/sposoby-pisat-konfiguracii.md)
  * [puppet](tools/upravlenie-konfiguraciyami/puppet.md)
  * [ansible](tools/upravlenie-konfiguraciyami/ansible.md)
  * [terraform](tools/upravlenie-konfiguraciyami/terraform.md)
* [VPN](tools/vpn/README.md)
  * [Pulse Secure SSL VPN](tools/vpn/pulse-secure-ssl-vpn.md)
  * [VPN WireGuard](tools/vpn/vpn-wireguard.md)
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
* [Мониторинг сети, приложений и событий](tools/monitoring-seti-prilozhenii-i-sobytii/README.md)
  * [Prometheus](tools/monitoring-seti-prilozhenii-i-sobytii/prometheus.md)
  * [Zabbix](tools/monitoring-seti-prilozhenii-i-sobytii/zabbix.md)
  * [snort](tools/monitoring-seti-prilozhenii-i-sobytii/snort.md)
  * [moloch](tools/monitoring-seti-prilozhenii-i-sobytii/moloch.md)

## Cloud

* [Papers](cloud/papers.md)
* [Google Cloud Platform (GCP)](cloud/google-cloud/README.md)
  * [GCP Components](cloud/google-cloud/gcp-components.md)
  * [GCP CLI](cloud/google-cloud/gcp-cli.md)
  * [Security](cloud/google-cloud/security/README.md)
    * [Get access to GCP via service-account \[json\]](cloud/google-cloud/security/get-access-to-gcp-via-service-account-json.md)
    * [PrivEsc](cloud/google-cloud/security/privesc.md)
    * [Papers](cloud/google-cloud/security/papers.md)
  * [Courses & Certifications](cloud/google-cloud/courses-and-certifications.md)
* [Azure](cloud/azure/README.md)
  * [Azure Start](cloud/azure/azure-start.md)
  * [Azure CLI](cloud/azure/azure-cli.md)
  * [Компоненты и механизмы](cloud/azure/komponenty-i-mekhanizmy/README.md)
    * [Azure Storage BLOB](cloud/azure/komponenty-i-mekhanizmy/azure-storage-blob.md)
    * [Подписанные URL (SAS)](cloud/azure/komponenty-i-mekhanizmy/podpisannye-url-sas.md)
  * [Papers And Resources](cloud/azure/papers-and-resources.md)
  * [Azure Security Center](cloud/azure/azure-security-center.md)
  * [Tools](cloud/azure/tools.md)
* [AWS](cloud/aws-1/README.md)
  * [Security](cloud/aws-1/security/README.md)
    * [Enumeration](cloud/aws-1/security/enumeration.md)
    * [AWS Lambda](cloud/aws-1/security/aws-lambda.md)
    * [Разные примеры](cloud/aws-1/security/raznye-primery.md)
    * [Learn Materials](cloud/aws-1/security/learn-materials.md)
  * [AWS Intro](cloud/aws-1/aws.md)
  * [AWS Basics](cloud/aws-1/aws-basics.md)
  * [AWS Components](cloud/aws-1/aws-components/README.md)
    * [Computing](cloud/aws-1/aws-components/computing.md)
    * [Storage](cloud/aws-1/aws-components/storage.md)
    * [Messaging](cloud/aws-1/aws-components/messaging.md)
    * [Business Productivity](cloud/aws-1/aws-components/business-productivity.md)
    * [Network and Content Delivery](cloud/aws-1/aws-components/network-and-content-delivery.md)
    * [Mobile](cloud/aws-1/aws-components/mobile.md)
    * [Databases](cloud/aws-1/aws-components/databases.md)
  * [AWS Testing](cloud/aws-1/aws-testing.md)
  * [Books & Papers](cloud/aws-1/books.md)
  * [Basic Work: Examples](cloud/aws-1/basic-work-examples/README.md)
    * [AWS Cli](cloud/aws-1/basic-work-examples/aws-cli.md)
    * [AWS SES](cloud/aws-1/basic-work-examples/aws-ses.md)
    * [S3 Bucket](cloud/aws-1/basic-work-examples/s3-bucket.md)
  * [Courses & Certifications](cloud/aws-1/courses-and-certifications.md)
* [Другие платформы](cloud/drugie-platformy.md)
* [OpenStack](cloud/openstack.md)
* [Покупка доменов](cloud/pokupka-domenov.md)
* [Tools](cloud/tools.md)

## Learning

* [Онлайн курсы](learning/onlain-kursy.md)
* [Подборки материалов](learning/podborki-materialov/README.md)
  * [DevOps](learning/podborki-materialov/devops.md)
  * [DevSecOps](learning/podborki-materialov/devsecops.md)
