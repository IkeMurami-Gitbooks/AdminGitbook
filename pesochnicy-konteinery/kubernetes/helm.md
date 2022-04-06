# helm

helm init - инициализирует репозиторий (при условии, что есть коннект до куба) - включает установку tiller на куб (в тч minikube)

Составные части:\
Deployment - как запускать контейнеры\
Service - как подключаться к контейнеру\
Netpol - политики взаимодействия между контейнерами (ака Firewall)\
Configmap\
Ingress: настройка контроллера

helm add repo \<name> [kubernetes-charts.storage.googleapis.com/](https://kubernetes-charts.storage.googleapis.com) - добавление дефолтоного репозитория

helm update repo&#x20;

helm search \<chart>

helm install \<name chart local> \<name-repo>/\<name-chart>

Установить чарт (локальный) на кубер: helm install \<name-chart-on-kube> \<helm path ./> --namespace \<namespace>





Дефолтные helm-charts для кучи всего: [https://github.com/helm/charts/tree/master/stable](https://github.com/helm/charts/tree/master/stable)

&#x20;

&#x20;**** \
****

****

