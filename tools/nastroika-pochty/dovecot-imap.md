# Dovecot (IMAP)

```
Install
$ sudo apt install dovecot-imapd dovecot-pop3d

Config Location
$ doveconf -n

Config
$ ln -s /etc/dovecot/dovecot.conf /var/run/dovecot/dovecot.conf
$ doveconf -nP > /etc/dovecot/dovecot.conf
$ 
```

```
1. Install:

$ sudo apt install dovecot-imapd dovecot-pop3d

2. Add protocols
В файле /etc/dovecot/dovecot.conf перечислим протоколы, с которыми будем работать:

protocols = pop3 pop3s imap imaps

Я сделал через добавление в директорию файлов:

echo 'protocols = $protocols pop3s' > /usr/share/dovecot/protocols.d/pop3s.protocol
echo 'protocols = $protocols imaps' > /usr/share/dovecot/protocols.d/imaps.protocol

3. Mail Location
В файле /etc/dovecot/conf.d/10-mail.conf проверяем значение параметра mail_location:

mail_location = mbox:~/mail:INBOX=/var/mail/%u

4. Restart Service
sudo /etc/init.d/dovecot restart

or

systemctl enable dovecot
systemctl start dovecot
```
