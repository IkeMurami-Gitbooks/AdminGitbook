# Работа с архивами

Сделать tar.gz из папки:

```
tar -zcvf OVPetrakov_eMAPT_2020_report.tar.gz report_exam
```

Сделать zip-архив

```
zip -r -9 test.zip test_dir/* test2_dir/* -x "test3_dir/*"
Архивируем рекурсивно test_dir и test2_dir, исключая test3_dir/*
```

Работа с zip-архивом

```
List:
$ unzip -l archive.zip

Целостность без распаковки:
$ unzip -t archive.zip

Разархивировать:
$ unzip www-archive.zip

в указанную директорию
$ unzip www-archive.zip -d /temp/

Файл в отдельности:
$ unzip www.archive.zip my-file.php
```
