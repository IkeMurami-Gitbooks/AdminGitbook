# Splunk

splunk vulns: [https://github.com/cnotin/SplunkWhisperer2](https://github.com/cnotin/SplunkWhisperer2)

ну смотри. там основной смысл что если ты знаешь админский пароль уровня приложения (админский пароль спланка), то ты можешь запустить в ОС код с правами той учетки из под которой приложение работает

у спланка агент позволяет выполнять код на машинах. это его фича. и довольна важная

интереснее всего пытаться заэксплуатировать на винде, потому что там агент чаще всего работает под SYSTEM LOCAL

а на линуксе часто запускают под порезанной учеткой

но здесь чтобы за эксплуатировать нужно знать админский пароль для агентов спланка. По моему опыту, его потенциально можно раздобыть (часто агенты устанавливают скриптами: либо баш, либо ansible и если найти подобный скрипт установки, то в нем будет пароль
