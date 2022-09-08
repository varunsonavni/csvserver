# The csvserver assignment

### Pulling the docker images with following command:

```
docker pull infracloudio/csvserver:latest
docker pull prom/prometheus:v2.22.0
```

### Find the port for the image

```
docker image inspect 8cb989ef80b5 | grep "tcp" | uniq | sed 's/"//g;s/ //g' | awk -F / '{print $1}'
```

### Run the docker container with following command:
```
docker run
```


Creating gencsv.sh and execute it to generate a file named inputFile.

### Run the docker with Env Var and Dir Mount and go inside container and check input file is there.

```
docker run --name csvserver2 -e CSVSERVER_BORDER=Orange -dp 9393:9300 -v /root/infra/csvserver/solution/inputFile:/csvserver/inputdata 8cb989ef80b5 tail -f /dev/null

docker exec -d csvserver ./csvserver
```

### Docker compose
```
docker-compose up
```
