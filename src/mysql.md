# MySQL

Make MySQL available on Mac

```bash
brew info mysql
mysql.server start
mysql -u root
```

First, initial setting

```bash
mysql_secure_installation
mysql -u root -p
```

It is necessary to take measures against garbled characters

```bash
echo -e "[mysqld]\ncharacter-set-server=utf8\n\n[client]\ndefault-character-set=utf8\n" | sudo tee /etc/mysql/conf.d/ja.cnf
mysql.server restart
```
