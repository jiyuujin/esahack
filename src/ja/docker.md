# Docker

## Tips

### Enable Docker Content Trust (DCT)

`~/.zshrc` に追加する

```bash
export DOCKER_CONTENT_TRUST=1
```

### I got `no space left on device`

未使用のコンテナを削除し、未使用の画像をクリーンアップすると機能します

```bash
docker system df

docker container prune
docker image prune
```

## Usage

- [MongoDB on Docker](mongodb_on_docker.md)
