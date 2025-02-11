# Docker / Kubernetes
[README.md](README.md)


## Kubernetes basics

Commandes uselles : 
```
kubectl get node 
kubectl create namespace testtoto
kubectl get ns
kubectl delete ns testtoto
kubectl api-ressources
kubectl explain namspace 
kubectl explain namspace.status
kubectl config get-contexts
```

### Pour modifier votre fichier ~/.kube/config, vous pouvez utiliser directement kubectl 
```
kubectl config set-context <context-name>
kubectl config use-context <context-name>
kubectl config set-cluster <cluster-name> --server=<server-url>
kubectl config set-credentials <user-name> --token=<token>
kubectl config view
```

### k9s (gestion directe dans l’interface)

1. Lancez k9s
2. Tapez :ctx pour afficher et changer de contexte.
3. Tapez :ns pour changer de namespace.


## Se connecter en amaint sur un équipement kubernetes de la CI

1- Se logger en root (ateme) sur la machine master 
```
ssh root@qas-nealive-k8s-cd25-0.lab1.anevia.com
```
2- Récupérer les namespaces présents
```
kubectl get namespaces
```
```
kubectl get ns
```
3- Récupérer le nom des PODs
```
kubectl get pod -A -o wide
```
4- Lancer un shell dans le pod : 
```
kubectl exec $NOM-DU-POD -n $NAMESPACE -it -- bash
```
ex:
```
kubectl exec nea-live-3-nea-dvr-sw-0 -n qas-nealive-cd25 -it -- bash
```
5- Se logguer en amaint ou monitor
```
su amaint
su monitor
```

### Environenment local pour test CI kubernetes


#### 1 - Installation de kubectl : Installer et configurer kubectl

```
sudo apt-get update && sudo apt-get install -y apt-transport-https
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
```

#### 2- Installer k9s :
```
wget https://github.com/derailed/k9s/releases/download/v0.32.5/k9s_linux_amd64.deb && apt install ./k9s_linux_amd64.deb && rm k9s_linux_amd64.deb
sudo dpkg -i k9s_linux_amd64.deb
```

#### 3- Installer helm : 

```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

#### 4- Ensuite, configurer le fichier kubeconf pour pouvoir se connecter aux équipements : https://gitlab.ateme.net/qas/tests-neadvr/-/settings/ci_cd 

Récupérer le contenu de la variable KUBECONFIG_FILE dans la section «Variable» disponible ici https://gitlab.ateme.net/qas/tests-neadvr/-/settings/ci_cd et le mettre en local dans le fichier ~/.kube/config

#### 5- Lancer l’application :
```
~$ k9s
```

*NB: Le redémarrage d’une machine peut s’effectuer en sélectionnant la machine cible puis executer la commande delete <ctrl-d>*


## Docker basics


### Copier un ficher dans un container

#### Du conteneur Docker vers la machine locale
```
sudo docker cp 135950565ad8:/geeksforgeeks.txt ~/Desktop/geeksforgeeks.txt
```
#### Du système local vers le conteneur Docker
```
sudo docker cp 135950565ad8:/geeksforgeeks.txt ~/Desktop/geeksforgeeks.txt
```
### Afficher les log d’un container 
```
docker logs [OPTIONS] <CONTAINER-NAME OR ID>
docker logs --follow <CONTAINER-NAME OR ID>
```

### Run containers 

```
docker compose up
```

In the background

```
docker compose up -d
```

#### List les containers en execution

```
docker container ls
```


### Ouvre une invite de commande bash dans le container id <CONTAINER_ID>

```
docker exec -it <CONTAINER_ID> bash
```

#### Execute une commande d'un container dans un repertoire hors du container

Monter un volume et executer une commande

```
docker run -v /home/gdaguet/src/tests-neadvr/benchmark/scripts:/home 837d5fd94483 /usr/local/bin/ateme-black /home
```


