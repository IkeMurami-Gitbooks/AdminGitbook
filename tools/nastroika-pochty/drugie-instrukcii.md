# Другие инструкции

by @Betepo\_Ok

Полноценный почтовый сервис должен включать в себя SMTP + IMAP протоколы.

SMTP отвечает за отправку почты. IMAP отвечает за прием почты.

Для SMTP хороший вариант - postfix Для IMAP - dovecot Для аутентификации опять же dovecot (postfix будет так же использовать dovecot)

Самый нормальный цикл статей: [https://www.linuxbabe.com/mail-server/setup-basic-postfix-mail-sever-ubuntu-14-04](https://www.linuxbabe.com/mail-server/setup-basic-postfix-mail-sever-ubuntu-14-04) [https://www.linuxbabe.com/mail-server/secure-email-server-ubuntu-16-04-postfix-dovecot](https://www.linuxbabe.com/mail-server/secure-email-server-ubuntu-16-04-postfix-dovecot) [https://wiki2.dovecot.org/HowTo/PostfixAndDovecotSASL](https://wiki2.dovecot.org/HowTo/PostfixAndDovecotSASL)

Еще какие-то статьи [https://habr.com/ru/post/258279/](https://habr.com/ru/post/258279/) [https://help.ubuntu.ru/wiki/postfix](https://help.ubuntu.ru/wiki/postfix) [https://losst.ru/ustanovka-postfix-ubuntu-s-dovecot](https://losst.ru/ustanovka-postfix-ubuntu-s-dovecot)
