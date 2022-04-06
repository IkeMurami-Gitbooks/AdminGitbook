# Установка

link: [https://www.jenkins.io/doc/book/installing/](https://www.jenkins.io/doc/book/installing/)

## Docker

Create [bridge network](https://docs.docker.com/network/bridge/)

```
docker network create jenkins
```

Create the following [volumes](https://docs.docker.com/storage/volumes/) to share the Docker client TLS certificates needed to connect to the Docker daemon and persist the Jenkins data.

```
docker volume create jenkins-docker-certs
docker volume create jenkins-data
```

In order to execute Docker commands inside Jenkins nodes, download and run the `docker:dind` (это по факту докер в докере) Docker image using the following [`docker container run`](https://docs.docker.com/engine/reference/commandline/container\_run/) command:

```
docker image pull docker:dind  // if not exist
docker container run \
  --name jenkins-docker \
  --rm \
  --detach \
  --privileged \
  --network jenkins \
  --network-alias docker \
  --env DOCKER_TLS_CERTDIR=/certs \
  --volume jenkins-docker-certs:/certs/client \
  --volume jenkins-data:/var/jenkins_home \
  --publish 2376:2376 \
  docker:dind
```

Download the `jenkinsci/blueocean` image and run it as a container in Docker using the following [`docker container run`](https://docs.docker.com/engine/reference/commandline/container\_run/) command:

```
docker image pull jenkinsci/blueocean  // if not exist
docker container run \
  --name jenkins-blueocean \
  --rm \
  --detach \
  --network jenkins \
  --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client \
  --env DOCKER_TLS_VERIFY=1 \
  --publish 8080:8080 \
  --publish 50000:50000 \
  --volume jenkins-data:/var/jenkins_home \
  --volume jenkins-docker-certs:/certs/client:ro \
  jenkinsci/blueocean
```

## Post installation

Go to http://localhost:8080

здесь спросят пароль админа. Для его получения лезем в логи или в конфиги jenkins. Для docker'а: `docker exec jenkins-blueocean cat /var/jenkins_home/secrets/initialAdminPassword`

Это так же пароль для пользователя admin (на случай, если пропустили создания пользователя в настройках). Если не знаешь какие плагины нужны, выбирай **Install suggested plugins**.
