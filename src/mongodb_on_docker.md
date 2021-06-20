# MongoDB on Docker

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
