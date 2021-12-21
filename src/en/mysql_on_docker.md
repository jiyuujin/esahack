# MySQL

Write Dockerfile.

```yml
version: '3'
services:
  mysql_db:
    image: mysql:5.7
    container_name: mysql_db
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_USER: root
      MYSQL_PASSWORD: password
      MYSQL_DATABASE: admin
      TZ: 'Asia/Tokyo'
    command: mysqld --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
    volumes:
    - ./docker/db/data:/var/lib/mysql
    - ./docker/db/my.cnf:/etc/mysql/conf.d/my.cnf
    - ./docker/db/sql:/docker-entrypoint-initdb.d
    ports:
    - 3306:3306
```

## Initialize

The database files will be automatically created on localhost.

```bash
docker-compose up -d
```

Access the `mongo_db` container.

```bash
docker-compose exec mongo_db bash
mongo admin -u mongo -p
```

[http://0.0.0.0:8081](http://0.0.0.0:8081) で確認する。

## MySQL in localhost

Make MySQL available for Mac.

```bash
brew info mysql
mysql.server start
mysql -u root
```

The first step is the initial setup.

```bash
mysql_secure_installation
mysql -u root -p
```

You will need to take measures to prevent garbled text.

```bash
echo -e "[mysqld]\ncharacter-set-server=utf8\n\n[client]\ndefault-character-set=utf8\n" | sudo tee /etc/mysql/conf.d/ja.cnf
mysql.server restart
```
