# Redis

Поднять в докере:

```yaml
version: '3.5'

services:
  redis:
    image: 'bitnami/redis:latest'
    ports:
      - "6379:6379"
    environment:
      - ALLOW_EMPTY_PASSWORD=yes

```

Запустить из CLI:

```
docker run -d -p 6379:6379 redis
```