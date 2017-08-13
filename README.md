# flask-containername
Flask App that Prints the Container Name and a Random UUID for Docker

## Docker Hub:
- https://hub.docker.com/r/rbekker87/flask-containername/

## Running the Container:

Create a Container from the Image:

```
$ docker pull rbekker87/flask-containername
$ docker run -itd --name flask-containername -p 80:5000 rbekker87/flask-containername
```

Test the Service:

```
$ curl http://127.0.0.1/
Container Hostname: 54e0e7d0d2cf , UUID: cb272d54-4542-41ed-a5af-c2424f715d7a
```

## Running with Docker Swarm:

```
$ docker network create appnet
$ docker service create \
--name web \
--publish 80:5000
--network appnet \
rbekker87/flask-containername
```

Test the Service:

```
$ curl http://0.0.0.0/
Container Hostname: 94f0e3d2d2dh , UUID: fj272d85-4542-31td-v5aw-d4714f755d7f
```
