# mysql

```
mysql -u USERNAME [-h HOST] [-P PORT] -p
show databases;
show tables;
use DBNAME;

# функции и процедуры
SHOW PROCEDURE STATUS;
SHOW FUNCTION STATUS;

Если определена функция sys_exec, то можно исполнить код (другого способа не нашел)    
```

Galera Cluster - это механизм/решение поднятия нескольких MySQL баз на разных хостах. О настройке: [https://netpoint-dc.com/blog/galera-cluster-principles-deployment-with-clustercontrol/](https://netpoint-dc.com/blog/galera-cluster-principles-deployment-with-clustercontrol/)

В .my.cnf могут храниться пароли и др настройки

Посмотреть настройки базы по умолчанию:&#x20;

```
shell> my_print_defaults client mysql
```

Если пароль замаскирован, добавить ключ -s
