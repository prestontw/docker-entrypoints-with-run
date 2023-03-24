Repo for testing `docker exec` and `docker run` with Docker containers with and without `ENTRYPOINT` specified.

### with entrypoint

```sh
docker build -t entrypoint:latest .
docker run --rm -it entrypoint:latest bash
```

produces

```
Hello from docker
```

### without entrypoint (with `CMD`)

```sh
docker build -t without-entrypoint:latest .
docker run --rm -it without-entrypoint:latest bash
```

gives an interactive shell

```
root@8b6b232f27c9:/app#
```
