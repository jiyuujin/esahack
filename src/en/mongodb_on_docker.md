# MongoDB

Write Dockerfile

```yml
version: '3'
services:
  mongo_db:
    # https://hub.docker.com/_/mongo/
    image: mongo
    ports:
      - 27017:27017
    volumes:
      - ./db:/data/db
      - ./configdb:/data/configdb
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: mongo
      MONGO_INITDB_ROOT_PASSWORD: password
      MONGO_INITDB_DATABASE: admin
```

## Initialize

Database files are automatically created in localhost

```bash
docker-compose up -d
```

Access the `mongo_db` container

```bash
docker-compose exec mongo_db bash
mongo admin -u mongo -p
```

Confirm at [http://0.0.0.0:8081](http://0.0.0.0:8081)

## Repositories

- [https://github.com/nekohack-oss/mongodb-tutorial](https://github.com/nekohack-oss/mongodb-tutorial)
