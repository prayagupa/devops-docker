

```
docker build -t "supply_chain:dockerfile" .
Sending build context to Docker daemon 2.048 kB
Step 1 : FROM ubuntu:latest
latest: Pulling from library/ubuntu

```

```
docker history supply_chain:dockerfile
```

```
docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
supply_chain        dockerfile          8f1874e00fb9        6 minutes ago       438.9 MB
<none>              <none>              786e7f41741d        8 minutes ago       438.9 MB
ubuntu              latest              45bc58500fa3        4 days ago          126.9 MB
```

```
docker run -p 5000:5000 suply_chain:dockerfile python clothing.py
```
