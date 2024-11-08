## Docker to restore mongo db backup in linux  or windows with wsl


### Start mongodb and mongp-express

1 - install docker

https://docs.docker.com/desktop/features/wsl/
https://docs.docker.com/engine/install/

2 - Create the volume for the data 

```bash
    mkdir -p .data/db
```

3 - Start mongo container

```bash
    docker compose up
```

### Restore mongo data

First you need to uncompress the  the tgz file in a folder

1 -  Copy the documents to mongodb container

```bash
docker cp /path_to_your_uncompressed_backup_folder/ mongodb:backups
```


2 - Restore the data
```bash
docker exec -it mongodb mongorestore /backups`
```