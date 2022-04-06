---
description: Программа для работы с реестром. Позволяет искать и изменять реестр
---

# reg

Все ключи по пути:\
`reg query HKLM\Software`

Все значения рекурсивно\
`reg query HKLM\Software\TightVNC\Server /s`

разделы:

* HKCU - HKEY\_CURRENT\_USER
* HKCR - HKEY\_CLASSES\_ROOT
* HKLM - HKEY\_LOCAL\_MACHINE
* HKU - HKEY\_USERS
* HKCC - HKEY\_CURRENT\_CONFIG&#x20;

HKLM и HKU - их можно просматривать через команды удаленного администрирования (типа psexec)

