# Banner Grabbing

Например, можно узнать, что за версия DNS-сервера

```
dig version.bind CHAOS TXT @ns1.example.com
nmap -Pn -p 53 --script dns-nsid ns1.example.com
```

