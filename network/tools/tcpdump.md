---
description: Ниже приведены примеры использования
---

# tcpdump

```
tcpdump
-i any - all interfaces
-n dont ip->dns
-nn - dont ip and ports -> dns...
-w dump.pcap
|------------------------------------|
-D - view all interfaces
```

{% embed url="https://superuser.com/questions/925286/does-tcpdump-bypass-iptables" %}

Пишем трафик с интерфейса rvi0 в файл trace.pcap\
root> tcpdump -i rvi0 -w trace.pcap
