---
description: Ниже представлены различные bat-ники в качестве примера
---

# Работа с bat-никами

## Запуск программы в отдельном потоке и закрытие консоли сразу:

```
@echo off
start my.exe
exit
```

Команда start - отвечает за запуск программы в другом потоке. Если ее не указать, то все будет выполняться в текущем процессе (=> пока не закроем my.exe, консоль не закроется).

## Пример bat-ника

```
@set dir=C:\
@echo off
MD C:\LogDir

rem Some message

:stage0
@If Exist "C:\SomeDir" (
    echo %date% %time% > C:\LogDir\test.log
    tasklist | find /C "some.exe"
    @if errorlevel 1 (
        echo shutdown >> C:\LogDir\some.log
        SHUTDOWN.EXE /r
    goto end
    )
    @If Exist "C:\SomeDir\some.bat" (
        ping -n 60 127.0.0.1 > nul
        call "C:\SomeDir\some.bat" >> C:\LogDir\some.log 
    goto end
    )
    sc config SomeService start= Demand
    sc start SomeService
    sc query SomeService | findstr /C:"STATE" | findstr /C:"RUNNING" > nul
    if %ERRORLEVEL%==0 (
        echo Service SomeService successfully started >> C:\LogDir\some.log
        exit /b
    )
    call "C:\SomeDir\some2.bat" reboot
    goto end
)
Else (
    goto stage1
)

rem Stage 2
:stage1
set /p "x=somestr" > "somefile.bat" < nul
set /p 'x=""somestr""' > "somefile1.bat" < nul
copy "somefile2.bat" "somefile3.bat"

goto end


:error
@If Exist "C:\LogDir" (
    shutdown /r /t 60 /f >>C:\LogDir\some.log
) ELSE (
    mkdir "C:\LogDir"
    shutdown /r /t 60 /f >>C:\LogDir\some.log
)
:end
exit
```
