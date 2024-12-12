# Docker basics

[README.md](README.md)

## Copier un ficher dans un container

### Du conteneur Docker vers la machine locale
```
sudo docker cp 135950565ad8:/geeksforgeeks.txt ~/Desktop/geeksforgeeks.txt
```
### Du système local vers le conteneur Docker
```
sudo docker cp 135950565ad8:/geeksforgeeks.txt ~/Desktop/geeksforgeeks.txt
```
## Afficher les log d’un container 
```
docker logs [OPTIONS] <CONTAINER-NAME OR ID>
docker logs --follow <CONTAINER-NAME OR ID>
```

## Run containers 

```
docker compose up
```

In the background

```
docker compose up -d
```

### List les containers en execution

```
docker container ls
```


## Ouvre une invite de commande bash dans le container id <CONTAINER_ID>

```
docker exec -it <CONTAINER_ID> bash
```

### Execute une commande d'un container dans un repertoire hors du container

Monter un volume et executer une commande

```
docker run -v /home/gdaguet/src/tests-neadvr/benchmark/scripts:/home 837d5fd94483 /usr/local/bin/ateme-black /home
```


