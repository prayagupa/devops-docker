docker-setup
----------------------

https://gist.github.com/prayagupd/69bbecb33af8abed1583



turn on proxy if neeeded 

```
docker build -t "supply_chain" .
Sending build context to Docker daemon 72.19 kB
Step 1 : FROM ubuntu:latest
 ---> 45bc58500fa3
Step 2 : MAINTAINER Andrew Odewahn "odewahn@oreilly.com"
 ---> Using cache
 ---> 4d8908e4bed5
Step 3 : RUN apt-get update
 ---> Using cache
 ---> ef136fcdde1e
Step 4 : RUN apt-get install -y python python-pip wget
 ---> Using cache
 ---> ffde31f32b49
Step 5 : RUN pip install Flask
 ---> Using cache
 ---> edc6b6b26ce8
Step 6 : ADD clothing.py /home/clothing.py
 ---> Using cache
 ---> 30ac34e183f4
Step 7 : WORKDIR /home
 ---> Using cache
 ---> 8f1874e00fb9
Successfully built 8f1874e00fb9
```

```
docker history supply_chain
```

```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
supply_chain        dockerfile          8f1874e00fb9        6 minutes ago       438.9 MB
<none>              <none>              786e7f41741d        8 minutes ago       438.9 MB
ubuntu              latest              45bc58500fa3        4 days ago          126.9 MB
```

```
docker run --name supply_chain_instance -i -t supply_chain

root@a8ea1e97cacb:/home# python clothing.py 
Pseudononymous Clothing store

```

```
docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
a8ea1e97cacb        supply_chain        "/bin/bash"         16 seconds ago      Up 15 seconds                           supply_chain_instance

```

```
docker ps -a -f status=running
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

```

delete nodes

```
docker rm $(docker ps -a -q)
```

issue
------------

`docker run -p 5000:5000 suply_chain:dockerfile` is not working.

Also tried

```
docker build -t supply_chain .
docker run -d -p 6379:6379 supply_chain

```


resources
-----------------

https://www.digitalocean.com/community/tutorials/docker-explained-using-dockerfiles-to-automate-building-of-images

http://odewahn.github.io/docker-jumpstart/building-images-with-dockerfiles.html

