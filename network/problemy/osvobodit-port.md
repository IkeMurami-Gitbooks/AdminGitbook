# Освободить порт

```
testserver # fuser -vn tcp 80
                     USER        PID ACCESS COMMAND
80/tcp:              root       1524 F.... nginx
                     www-data   1525 F.... nginx

testserver # kill -9 1525
```
