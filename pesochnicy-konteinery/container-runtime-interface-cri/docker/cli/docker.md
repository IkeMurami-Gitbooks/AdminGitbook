# docker cli part2

## Volumes

Подключение разделов в процессе запуска контейнера (например, если надо передать какие-то файлы на обработку):

```
docker run --rm -it -v /path/to/dir/on/home:/path/to/dir/on/container ...
```

Можно устанавливать права сразу:

```
... -v /path1:/path2:ro ...
```

## Работа с логами

```
Посмотреть логи
docker logs <container_name> 
    --timestamps - писать время
    --since ГГГГ-ММ-ДД
    --since ГГГГ-ММ-ДДТЧЧ (ex: 2018-01-30Т11:00)
    --tail N - последние n строк
    -f, --follow - непрерывный вывод

Узнать, где лежат:
docker inspect --format='{{.LogPath}}' <container_name>
    

```

## Информация о занимаемом объеме памяти

```
docker system df  - disk usage
docker system info
```

## Ограничение сети

```
docker run --rm -it --network none myimage ...
```

Другие сетевые адаптеры (можно делать свои):

* bridge — сеть между контейнерами на одном хосте (default)
* overlay — сеть между контейнерами на разных хостах
* macvlan —&#x20;
* ...
* none

## Перенос директории с образами в новую папку

link: [https://linuxconfig.org/how-to-move-docker-s-default-var-lib-docker-to-another-directory-on-ubuntu-debian-linux](https://linuxconfig.org/how-to-move-docker-s-default-var-lib-docker-to-another-directory-on-ubuntu-debian-linux)

## Ограничение общих ресурсов

Есть такая проблема. Пусть есть несколько контейнеров, запущенных на одной машине. В случае, если один контейнер выедает все ресурсы (например озу), то от этого падают все контейнеры. Такое поведение не приемлимо, если есть контейнеры критичные и которые by design не могут выжирать столько ресурсов.&#x20;

Решение - разделять важные и о не очень контейнеры на cgroups

У докера есть опция —cgroup-parent - ты можешь сделать цгруппу где ограничить общую память до 14 ГБ, а потом внутри запускать безлимитные контейнеры, например (или выставить дополнительные лимиты для контейнеров внутри).

или сделать то же самое через systemd

[https://stackoverflow.com/questions/46408673/docker-17-06-ce-default-container-memory-limit-on-shared-host-resources/46557336#46557336](https://stackoverflow.com/questions/46408673/docker-17-06-ce-default-container-memory-limit-on-shared-host-resources/46557336#46557336) Например вот ответ где объясняется как.
