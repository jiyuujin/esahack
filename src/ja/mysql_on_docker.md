# MySQL

Dockerfile を書く。

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

データベースファイルは自動的に localhost に作成される。

```bash
docker-compose up -d
```

mongo_db` コンテナにアクセスする。

```bash
docker-compose exec mongo_db bash
mongo admin -u mongo -p
```

[http://0.0.0.0:8081](http://0.0.0.0:8081) で確認する。

## MySQL in localhost

Mac で MySQL を利用できるようにする。

```bash
brew info mysql
mysql.server start
mysql -u root
```

まずは初期設定です。

```bash
mysql_secure_installation
mysql -u root -p
```

文字化け対策が必要です。

```bash
echo -e "[mysqld]\ncharacter-set-server=utf8\n\n[client]\ndefault-character-set=utf8\n" | sudo tee /etc/mysql/conf.d/ja.cnf
mysql.server restart
```
