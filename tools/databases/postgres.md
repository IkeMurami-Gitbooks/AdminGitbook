# postgres

```
psql -h host -p port -W <database> <user>
-W - указать пароль далее
```

```
\l - databases
\dt - таблицы
```

```
Дамп базы: дампится в етекстовик. Все потом легко читается


pg_dump -U sber_user -W sber_db > test.sql
```
