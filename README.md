# Purpose

Docker-compose environment for the BTA project:

https://bitbucket.org/iwseclabs/bta

# Build / Run

```
docker-compose up -d
```

# Use

Attach to the bta container:

```
docker exec -ti bta /bin/bash
```

Within the container, start importing data and then have fun with bta:

```
btaimport -C mongodb::mabase ntds.dit
```
