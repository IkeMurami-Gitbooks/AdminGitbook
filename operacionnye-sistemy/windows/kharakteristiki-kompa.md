# Характеристики компа

Узнать модель материнская платы:\
wmic baseboard get product

```
ОЗУ:
wmic memorychip get Manufacturer,Capacity,PartNumber,Speed,DeviceLocator
Количество слотов под оперативу:
wmic memphysical get MemoryDevices
Максимально возможный объем оперативной памяти:
wmic memphysical get MaxCapacity
Полный объем установленной памяти:
systeminfo | find "Полный объем физической памяти"
systeminfo | find "Total Physical Memory"
Форм-фактор модулей
wmic memorychip get FormFactor
8 - DIMM
12 - SODIMM (ноуты)
Тип памяти:
wmic memorychip get MemoryType
0 - не удалось определить спецификацию
20 - DDR
21 - DDR2
22 - DDR2 FB=DIMM
24 - DDR3
25 - FBD2
Напряжение:
wmic memorychip get ConfiguredVoltage
```
