# Практика

## Установка

Установить можно через docker-контейнер

Проверяем работоспособность:

```
# для удобства запомним адрес в переменную
#export ES_URL=$(docker-machine ip dev):9200
export ES_URL=localhost:9200

curl -X GET $ES_URL
```

Пример ответа:

```javascript
{
  "name" : "Heimdall",
  "cluster_name" : "elasticsearch",
  "version" : {
    "number" : "2.2.1",
    "build_hash" : "d045fc29d1932bce18b2e65ab8b297fbf6cd41a1",
    "build_timestamp" : "2016-03-09T09:38:54Z",
    "build_snapshot" : false,
    "lucene_version" : "5.4.1"
  },
  "tagline" : "You Know, for Search"
}
```

## Использование

### Добавление данных

На примере постов

```
# Добавим документ c id 1 типа post в индекс blog.
# ?pretty указывает, что вывод должен быть человеко-читаемым.

curl -XPUT "$ES_URL/blog/post/1?pretty" -d'
{
  "title": "Веселые котята",
  "content": "<p>Смешная история про котят<p>",
  "tags": [
    "котята",
    "смешная история"
  ],
  "published_at": "2014-09-12T20:44:42+00:00"
}'
```

Ответ сервера

```javascript
{
  "_index" : "blog",
  "_type" : "post",
  "_id" : "1",
  "_version" : 1,
  "_shards" : {
    "total" : 2,
    "successful" : 1,
    "failed" : 0
  },
  "created" : false
}
```

ES автоматически создал [индекс](https://www.elastic.co/guide/en/elasticsearch/reference/current/glossary.html#glossary-index) blog и [тип](https://www.elastic.co/guide/en/elasticsearch/reference/current/glossary.html#glossary-type) post. Можно провести условную аналогию: индекс — это база данных, а тип — таблица в этой БД. Каждый тип имеет свою схему — [mapping](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/glossary.html#glossary-mapping), также как и реляционная таблица. Mapping генерируется автоматически при индексации документа:

```
# Получим mapping всех типов индекса blog
curl -XGET "$ES_URL/blog/_mapping?pretty"
```

Пример ответа (комменты автора):

```javascript
{
  "blog" : {
    "mappings" : {
      "post" : {
        "properties" : {
          /* "content": "<p>Смешная история про котят<p>", */ 
          "content" : {
            "type" : "string"
          },
          /* "published_at": "2014-09-12T20:44:42+00:00" */
          "published_at" : {
            "type" : "date",
            "format" : "strict_date_optional_time||epoch_millis"
          },
          /* "tags": ["котята", "смешная история"] */
          "tags" : {
            "type" : "string"
          },
          /*  "title": "Веселые котята" */
          "title" : {
            "type" : "string"
          }
        }
      }
    }
  }
}
```

Стоит отметить, что ES не делает различий между одиночным значением и массивом значений. Например, поле title содержит просто заголовок, а поле tags — массив строк, хотя они представлены в mapping одинаково. Позднее мы поговорим о маппинге более подобно.

### Запросы

#### Извлечение документа по его id

```
# извлечем документ с id 1 типа post из индекса blog
curl -XGET "$ES_URL/blog/post/1?pretty"
```

```javascript
{
  "_index" : "blog",
  "_type" : "post",
  "_id" : "1",
  "_version" : 1,
  "found" : true,
  "_source" : {
    "title" : "Веселые котята",
    "content" : "<p>Смешная история про котят<p>",
    "tags" : [ "котята", "смешная история" ],
    "published_at" : "2014-09-12T20:44:42+00:00"
  }
}
```

В ответе появились новые ключи: `_version` и `_source`. Вообще, все ключи, начинающиеся с `_` относятся к служебным.

Ключ `_version` показывает версию документа. Он нужен для работы механизма оптимистических блокировок. Например, мы хотим изменить документ, имеющий версию 1. Мы отправляем измененный документ и указываем, что это правка документа с версией 1. Если кто-то другой тоже редактировал документ с версией 1 и отправил изменения раньше нас, то ES не примет наши изменения, т.к. он хранит документ с версией 2.

Ключ `_source` содержит тот документ, который мы индексировали. ES не использует это значение для поисковых операций, т.к. для поиска используются индексы. Для экономии места ES хранит сжатый исходный документ. Если нам нужен только id, а не весь исходный документ, то можно отключить хранение исходника.

Если нам не нужна дополнительная информация, можно получить только содержимое \_source:

```
curl -XGET "$ES_URL/blog/post/1/_source?pretty"
```

```javascript
{
  "title" : "Веселые котята",
  "content" : "<p>Смешная история про котят<p>",
  "tags" : [ "котята", "смешная история" ],
  "published_at" : "2014-09-12T20:44:42+00:00"
}
```

Также можно выбрать только определенные поля:

```
# извлечем только поле title
curl -XGET "$ES_URL/blog/post/1?_source=title&pretty"
```

```javascript
{
  "_index" : "blog",
  "_type" : "post",
  "_id" : "1",
  "_version" : 1,
  "found" : true,
  "_source" : {
    "title" : "Веселые котята"
  }
}
```

### Сортировка

```
# найдем последний пост по дате публикации и извлечем поля title и published_at
curl -XGET "$ES_URL/blog/post/_search?pretty" -d'
{
  "size": 1,
  "_source": ["title", "published_at"],
  "sort": [{"published_at": "desc"}]
}'
```

### Фильтры и запросы

Используем запрос [range](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-range-query.html) в контексте filter:

```
# получим посты, опубликованные 1ого сентября или позже
curl -XGET "$ES_URL/blog/post/_search?pretty" -d'
{
  "filter": {
    "range": {
      "published_at": { "gte": "2014-09-01" }
    }
  }
}'
```

#### Фильтрация по тегам

Используем [term query](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-term-query.html) для поиска id документов, содержащих заданное слово:

```
# найдем все документы, в поле tags которых есть элемент 'котята'
curl -XGET "$ES_URL/blog/post/_search?pretty" -d'
{
  "_source": [
    "title",
    "tags"
  ],
  "filter": {
    "term": {
      "tags": "котята"
    }
  }
}'
```

#### Полнотекстовый поиск

Используем [match query](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query.html) для поиска id документов, содержащих заданное слово:

```
# source: false означает, что не нужно извлекать _source найденных документов
curl -XGET "$ES_URL/blog/post/_search?pretty" -d'
{
  "_source": false,
  "query": {
    "match": {
      "content": "история"
    }
  }
}'
```

### Анализаторы

[Анализаторы](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis.html) нужны, чтобы преобразовать исходный текст в набор токенов.

В ES есть несколько [стандартных анализаторов](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-analyzers.html). Например, анализатор [russian](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-lang-analyzer.html#russian-analyzer).

```
# используем анализатор standard       
# обязательно нужно перекодировать не ASCII символы
curl -XGET "$ES_URL/_analyze?pretty&analyzer=standard&text=%D0%92%D0%B5%D1%81%D0%B5%D0%BB%D1%8B%D0%B5%20%D0%B8%D1%81%D1%82%D0%BE%D1%80%D0%B8%D0%B8%20%D0%BF%D1%80%D0%BE%20%D0%BA%D0%BE%D1%82%D1%8F%D1%82"

# используем анализатор russian
curl -XGET "$ES_URL/_analyze?pretty&analyzer=russian&text=%D0%92%D0%B5%D1%81%D0%B5%D0%BB%D1%8B%D0%B5%20%D0%B8%D1%81%D1%82%D0%BE%D1%80%D0%B8%D0%B8%20%D0%BF%D1%80%D0%BE%20%D0%BA%D0%BE%D1%82%D1%8F%D1%82"


```

Соотв, можно писать свои анализаторы и преобразователи, которые как-то обрабатывают данные на стороне elastic.

### Полнотекстовый поиск с поддержкой выражений

```
# найдем документы, в которых встречается слово 'истории'
# query -> simple_query_string -> query содержит поисковый запрос
# поле title имеет приоритет 3
# поле tags имеет приоритет 2
# поле content имеет приоритет 1
# приоритет используется при ранжировании результатов
curl -XPOST "$ES_URL/blog2/post/_search?pretty" -d'
{
  "query": {
    "simple_query_string": {
      "query": "истории",
      "fields": [
        "title^3",
        "tags^2",
        "content"
      ]
    }
  }
}'
```

Запрос может содержать специальные символы, например:

```
"\"fried eggs\" +(eggplant | potato) -frittata"
```

Синтаксис запроса:

```
+ signifies AND operation
| signifies OR operation
- negates a single token
" wraps a number of tokens to signify a phrase for searching
* at the end of a term signifies a prefix query
( and ) signify precedence
~N after a word signifies edit distance (fuzziness)
~N after a phrase signifies slop amount
```

```
# найдем документы без слова 'щенки'
curl -XPOST "$ES_URL/blog2/post/_search?pretty" -d'
{
  "query": {
    "simple_query_string": {
      "query": "-щенки",
      "fields": [
        "title^3",
        "tags^2",
        "content"
      ]
    }
  }
}'

# получим 2 поста про котиков
```
