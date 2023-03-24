Repo for testing `docker exec` and `docker run` with Docker containers with and without `ENTRYPOINT` specified.

### with entrypoint

#### `docker run`

```sh
docker build -t entrypoint:latest .
docker run --rm -it entrypoint:latest bash
```

produces

```
Hello from docker
```

#### `docker exec`

```sh
docker run --rm -it entrypoint:latest
# in another shell
docker ps -a
docker exec -it <container ID> bash
```

Drops you in an interactive shell:

```
root@adf0428d4e6f:/app#
```

### without entrypoint (with `CMD`)

#### `docker run`

```sh
docker build -t without-entrypoint:latest .
docker run --rm -it without-entrypoint:latest bash
```

gives an interactive shell

```
root@8b6b232f27c9:/app#
```

#### `docker exec`

```sh
docker run --rm -it without-entrypoint:latest
# in another shell
docker ps
docker exec -it <container ID> bash
```

Drops you in an interactive shell:

```
root@bc8c8479680d:/app#
```
