# drone-test

run drone server with

```
docker run --volume=/var/local/lib/drone:/data --env-file .secrets/drone-server.env --publish 80:80 --restart always --detach --name drone drone/drone:1
```

configure drone client with

```
. .secrets/drone-client.sh
```

run runner with

```
docker run -d -v /var/run/docker.sock:/var/run/docker.sock --env-file .secrets/drone-runner.env -p 3000:3000 --restart always --name runner drone/drone-runner-docker:1
```

trigger first build with 

```
curl -X POST -i http://localapp.fdsk.co.uk/api/repos/fdsk-tests/drone-test/builds -H "Authorization: Bearer "
```
