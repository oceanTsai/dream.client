# environment
- bun 1.0.7
- docker 24.0.6

# environment verification
- Check if bun.js exists in your mac. You can run ```bun -v``` in your terminal. If you see a version number, it means you have bun.js.
  If not, please run ```curl -fsSL https://bun.sh/install | bash -s "bun-v1.0.7"```.

- Check if docker exists in your mac. You can run ```docker -v``` in your terminal. If you see a version number, it means you have docker. If not, please run ```brew install docker --cask```

# Init Project Step by Step
1. Install dependency lib. ```bun install```.
2. Modify file permissions. ```chmod 1777 ./bun.lockb```
3. Remove node_modules ```rm -rf node_modules```
3. Build docker image. ```docker image build -t dream-web-img .```
4. Create and Run docker container ```docker container run -it --name dream-web -v `pwd`/:/user/web -p 8282:8080 -d dream-web-img```

# Open browser
- ```http://localhost:8282/```

# Re Run Container
1. If container not Run, please run ```docker start container_id```.

# About Bun command
[Bun Command](https://bun.sh/docs/cli/add)

**Add Package**

To add a particular package:
```shell
bun add preact
```

To specify a version, version range, or tag:
```shell
bun add zod@3.20.0
bun add zod@^3.0.0
bun add zod@latest
```


add a package as a dev dependency ("devDependencies"):
```shell
bun add --dev @types/react
bun add -dev @types/react
```

**Remove Package**
```shell
bun remove ts-node
```

# About Docker command
- ```docker ps```, list running Docker container.
- ```docker ps -a```, list all Docker containers, including the stopped ones.

The form looks like
| CONTAINER ID | IMAGE | COMMAND | CREATED | STATUS | PORTS | NAMES |
|  ----  | ----  | ----  | ----  | ----  |----  |----  |
| 6b730c6b2a63 | dream-web-img | "docker-entrypoint.s…" |   50 minutes ago |   Exited (137) 47 minutes ago |  | dream-web | 

- ```docker stop container_id```, stop docker Container.

- ```docker start container_id```, start stopped containers.

- ```docker restart container_id```, restart containers.

- ```docker rm container_id```, remove docker container.

- ```docker rmi image_id```, remove docker image.

- ```docker logs container_id```, show docker container logs.
