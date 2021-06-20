# Docker

## Tips

### Enable Docker Content Trust (DCT)

Add to `~/.zshrc`

```bash
export DOCKER_CONTENT_TRUST=1
```

### I got `no space left on device`

It works when I deleted an unused container, and clean up unused images

```bash
docker system df

docker container prune
docker image prune
```

## Usage

- [MongoDB on Docker](mongodb_on_docker.md)
