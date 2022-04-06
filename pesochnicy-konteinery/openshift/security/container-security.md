# Container Security

## Отдельные заметки

Container Engine — предлагает набор инструментов для таких задач как создание и запуск контейнеров.

CRI — Container Runtime Interface

CRI-O — Container Engine of OpenShift. Как реализация Kubernetes CRI, CRI-O позволяет использовать среды выполнения, совместимые с OCI (Open Container Initiative).

OCI — Open Container Initiative — проект Linux Foundation, по разработке открытых стандартов для виртуализации на уровне операционной системы, в первую очередь контейнеров Linux. В настоящее время разрабатываются и используются две спецификации: спецификация среды выполнения (runtime-spec) и спецификация изображения (image-spec).

CRI-O — контейнерный движок по умолчанию для OpenShift 4, заменяющий Docker, который был по умолчанию в OpenShift 3.11.

## CRI-O

Для запуска контейнеров вне OpenShift, используется **podman** (on RHEL host).

В архитектуре OpenShift не приветствутся обращение напрямую к CRI-O, однако это можно сделать с помощью команды **crictl** с любой ноды openshift и посмотреть например логи на другом контейнере:

```
# crictl ps

49f7832d3c4b9 quay.io/openshift-release-dev/ocp-v4.0-art-dev@sha256…      
    5 hours ago   Running   openvswitch    0b989143485eb

# crictl logs 49f7832d3c4b9

```

Почитать про возможности crictl: [https://github.com/kubernetes-sigs/cri-tools/blob/master/docs/crictl.md](https://github.com/kubernetes-sigs/cri-tools/blob/master/docs/crictl.md)\
Про разницу podman и crictl: [https://www.openshift.com/blog/crictl-vs-podman](https://www.openshift.com/blog/crictl-vs-podman)



