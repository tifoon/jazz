# Goal

Build apache-mesos code ground up using Docker

# Build

```
docker build -t apache-mesos .
```

# Run

```
 docker run -it -p 5050:5050 -p 5051:5051 -p 2181:2181 apache-mesos
```
