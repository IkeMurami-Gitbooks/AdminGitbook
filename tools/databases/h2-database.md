# H2 Database

База написана на чисто Java. Поддерживает JDBC API. Очень легковесна. Поддерживает In-Memory режим.

Примеры dbUrl:

```
jdbc:h2:mem:test
jdbc:h2:mem:test;MODE=MYSQL;LOCK_MODE=0;DB_CLOSE_ON_EXIT=false;DB_CLOSE_DELAY=-1
jdbc:h2:tcp://localhost:1521/test
jdbc:h2:test

Общий вид:
jdbc:h2:<address>:<name>

```

## Security

Link: [https://codewhitesec.blogspot.com/2019/08/exploit-h2-database-native-libraries-jni.html](https://codewhitesec.blogspot.com/2019/08/exploit-h2-database-native-libraries-jni.html)
