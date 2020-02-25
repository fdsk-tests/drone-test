# drone-test

run drone server with

```
docker run --volume=/var/local/lib/drone:/data --env-file .secrets/.drone.env --publish 80:80 --restart always --detach --name drone drone/drone:1
```

configure drone client with

```
. .secrets/.drone-client.sh
```
