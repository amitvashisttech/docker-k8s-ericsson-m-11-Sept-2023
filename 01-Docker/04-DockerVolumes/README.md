
# Docker Volumes

Docker has volumes that are free-floating filesystems. So there is no need to be connected to a particular container. You can use volumes mounted from data-only containers for portability. As per Docker 1.9.0, it comes with the named volumes that replace data-only containers.




## Volume Commands

#### List the existimg volumes

```
  docker volume ls 
```

#### To create volumes

```
  docker volume create
```

#### To inspect the volumes

```
  docker volume inspect <volume-name>
```


#### To remove volumes

```
  docker volume rm <volume-name>
```

#### To mount the volumes into containers

```
   docker run -it --name volume-test-1 -v my-vol:/app ubuntu
```

#### To mount the volumes in readonly mode into containers

```
   docker run -it --name volume-test-1 -v my-vol:/app:ro ubuntu
```


