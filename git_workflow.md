# Git forkwlow

[README.md](README.md)


## Initier un projet Git

1. Installer Git

```
sudo apt update
sudo apt install git
```

2. Configurer Git (une seule fois)

```
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

3. Créer un nouveau répertoire de projet

```
mkdir nom_du_projet
cd nom_du_projet
```

4. Initialiser un dépôt Git

```
git init
```

5. Ajouter des fichiers au dépôt

```
git add .
```

6. Faire un premier commit


```
git commit -m "Premier commit"
```

7. Ajouter un dépôt distant (optionnel)

```
git remote add origin https://github.com/votre-utilisateur/nom_du_projet.git
git remote add origin https://github.com/970M/How-To.git
```

8. Pousser vos modifications vers le dépôt distant

```
git push -u origin master
```


## Development with git

### 1. Cloner le projet

```
git clone git@gitlab.ateme.net:qas/tests-neadvr.git
```

### 2. Configurer le projet
    

### 3. Checkout et création de sa branche perso en local

```
$ git checkout -b <trigram>-<branch identifier>
```

### 4- Faire les modifications et commiter en local

### 5- Mettre à jour son travail en incorporant les nouveaux commits de la branche master

```
git checkout master
git pull
git checkout <trigram>-<branch identifier>
git rebase origin/master
```

Idem avec squash des commits (= réunir les commits en un seul) : 

```
git checkout master
git pull
git checkout <trigram>-<branch identifier>
git rebase -i origin/master
```

NB: rebase interactif

### 6- Envoyer les modifications sur le projet en remote

Vous pouvez faire chaque changement, valider et envoyer votre souhait à votre branche à tout moment. Chaque poussée de votre branche déclenchera l'intégration continue ("CI") et déclenchera ainsi une construction. 

Pousser ma branche locale vers ma branche remote:

```
git checkout <trigram>-<branch identifier>
git push -u origin <trigram>-<branch identifier>
```

Idem si la branche locale à dérivée (nombre de commits différent suite un rebase 
interactif, historique…) : 

```
git checkout <trigram>-<branch identifier>
git push -f -u origin <trigram>-<branch identifier>
```


## Tricks

### reset // Revenir sur une version antérieure (merge tous les commits en un seul et 
conserve les modifs dans la zone d'index avec l'option soft seulement)

```
git checkout <trigram>-<branch identifier>
git reset --soft #TAG
```

### push // Mettre à jour ma branche distante avec ma branche locale qui a dérivé (historique et nombre de commits différent par suite d'un reste soft voir un rebase)

i.e. on force la branche distante à être identique à la branche locale que l'on pousse :   

```
git checkout <trigram>-<branch identifier>
git push -f -u origin <trigram>-<branch identifier>
```

### rebase // Rebaser tout en mergeant les commits (possibilité de les choisir): Rebase interactif :

```
git checkout <trigram>-<branch identifier>
git rebase -i origin/master
```

(/!\ Message de commit)

Nb: A faire pour se synchroniser avec la branche master
Ecrase/corrige le dernier commit
git commit --ament --no-edit
Merge de ma branche remote sur le master

Automatique via la GUI

### pull //Mettre à jour ma branche local avec ma branche distante suite une prise en compte de remarque pendant un MR

```
git checkout <trigram>-<branch identifier>
git pull
```

NB: Met à jour la branche sur laquelle on est... 

### fetch // Récupérer une branche distante en local

git fetch origin <branch-namek>
checkout // Rétablir un fichier à un commit précédent
git checkout #TAG <filename>
Supprimer en local le nom de branche remote qui n’existent plus 
git remote prune origin
git fetch <remote>

La commande git remote update remote est la même que la commande git fetch remote (Il y avait quelques bugs dans certaines versions de Git qui les rendaient différentes, mais elles sont censées faire la même chose.) Avec --prune, le processus de mise à jour supprime simplement tous les noms de suivi à distance qui existent dans votre référentiel, mais ne correspondent plus à un nom de branche dans le référentiel à remote.

### Supprimer une branche

Branche locale

```
git branch -d [nom-de-ma-branche]
git branch -D [nom-de-ma-branche]
```
-D : --delete --force

Branche distante 

```
git push [origin] --delete [nom-de-ma-branche]
```

### cherry pick // Mettre un commit d’une branche sur une autre

Dans cet exemple, nous avons construit, disons que nous voulions utiliser commit #TAG en[nom-de-ma-branche]. Nous veillons tout d'abord à ce que nous travaillions sur la[nom-de-ma-branche]branche.
git checkout [nom-de-ma-branche]

Ensuite, nous exécutons le pick-chérie avec la commande suivante:

```
git cherry-pick #TAG
```


## Message de commits


        <type>(<portée>): <sujet>

            <description>

### \<type\>

Le type nous informe du type de commit. 9 types sont disponibles :
build : changements qui affectent le système de build ou des dépendances externes (npm, make…)

***ci*** : changements concernant les fichiers et scripts d’intégration ou de configuration (Travis, Ansible, BrowserStack…)

***feat*** : ajout d’une nouvelle fonctionnalité

***fix*** : correction d’un bug

***perf*** : amélioration des performances

**refactor** : modification qui n’apporte ni nouvelle fonctionalité ni d’amélioration de performances

***style*** : changement qui n’apporte aucune alteration fonctionnelle ou sémantique (indentation, mise en forme, ajout d’espace, renommante d’une variable…)

***docs*** : rédaction ou mise à jour de documentation

***test*** : ajout ou modification de tests

***revert*** : annuler un précédent commit. Dans ce cas, le message prend la forme suivante :
revert sujet du commit annulé hash du commit annulé

### \<portée\>

add, change, update, remove

### \<sujet\>

La description ...


## Documentation

### Git stash

https://www.atlassian.com/git/tutorials/saving-changes/git-stash
 
### Gitlab CI/CD

https://doc-rd.anevia.com/files/extract/rd-bible/master/
https://doc-rd.anevia.com/files/extract/rd-bible/master/gitlab/index.html
https://docs.gitlab.com/ee/ci/yaml/gitlab_ci_yaml.html 


