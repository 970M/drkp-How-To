# BASH cheat sheet

[README.md](README.md)


## Watch the command output change over time

```
watch -n 2 "COMMAND"
```
```
watch -n 2 "/etc/init.d/pgbouncer status"
```


## Command with loop

```
for i in `ls` ; do echo $i; done
```
```
for proc in `ps -edf | grep -i create_npvrs.py | awk '{print $2}'`; do kill $proc; done
```

### Monitoring espace disque
```
while true; do du -s /* 2>/dev/null | sort -h > /mnt/streams0/disque_$(date +%s).txt; df -h /; sleep 1; done
```

## Vérifier l'espace disque sur clé usb

```
sudo parted /dev/sda
(parted) print
```

## System

### RAM

```
free -m -h
vmstat -s -S M
cat /proc/meminfo
```

### Network

```
tcpdump -i eth6 -A -s 10240 'tcp port 80' | grep -v IP | egrep --line-buffered "..(GET |\.HTTP\/|POST |HEAD )|^[A-Za-z0-9-]+: " |sed -r 's/..(GET |HTTP\/|POST |HEAD )/\n\n\1/g'
```


## Changer la carte graphique

```
prime-select query
prime-select intel
prime-select --help
sudo prime-select intel
prime-select query
```

## Process

```
pstree
```

*Press Alt+F2, then in the resulting box type r and press the Enter key. This will temporarily resolve the issue by restarting the GUI desktop manager.*


## Rechercher des fichiers contenant EXPR
grep -ril EXPR ./


## Afficher la liste des utilisateurs :

```
cat /etc/passwd | awk -F: '{print $ 1}'
```

## Afficher la liste des groupes
```
cat /etc/group | awk -F: '{print $ 1}'
```

## Liste les membre d'un groupe
```
getent group groupname 
cat /etc/group
```

# =============================================================================
# [[ GESTION DES PERMISSIONS ]] 
# =============================================================================

### Les droits sont drwxrwx— (770) pour les répertoires et -rwxrwx—- (770) pour les fichiers :
chmod -R 770 monrep

### drwxrwx— (770) pour les répertoires et -rw-rw—- (660) pour les fichiers : 

chmod -R u-x,g-x,u+X,g+X monrep

sudo chmod 0750 
# =============================================================================
# [[ TEMPLATE ]] 
# =============================================================================


### [[ Interblocage sur port 8080 ]] 
lsof -i TCP:8080 | grep LISTEN

# =============================================================================
# [[ LISTE DES LOGICIELS INSTALES ]] 
# =============================================================================

ls /usr/share/applications | awk -F '.desktop' ' { print $1}'

dpkg --list
snap list
apt list --installed

# Supprimer programme
sudo apt-get --purge remove program

# =============================================================================
# [[ ECRIRE EN COULEUR ]] 
# =============================================================================

echo -e "[\033[35m$USER\033[30m@\033[32m$HOSTNAME\033[30m:\033[31m$PWD\033[30m]$ "

970M-Database/970M/0000
####### [[ Reconfigurer phpmyadmin ]] #######

sudo dpkg-reconfigure phpmyadmin

phpmyadminGD@localhost / 0000
phpmyadmin_root

# =============================================================================
# SERVEUR LAMP
# =============================================================================

####### [[ START/STOP mySql ]] #######

#--- lancer mysql :
sudo /etc/init.d/mysql start


####### [[ START/STOP APACHE SERVER ]] #######

sudo systemctl start apache2

####### [[ CONFIG USER PHPMYADMIN ]] #######

sudo cat /etc/mysql/debian.cnf

####### [[ Executer des commandes sudo dans un script ]] #######
#--- Donner le fichier à root
sudo chown root le_script.sh

#--- mettre le bit setuid
sudo chmod +s le_script.sh


# =============================================================================
# [[ ATOM ]] 
# =============================================================================

# intallation tbd ...

# Package 

# platformio-ide-terminal
apm install platformio-ide-terminal 
# 
apm install atom-ide-base
apm install ide-python


# =============================================================================
# [[ GIT ]]
# =============================================================================

#######################################
# [[ 1- Installer Git ]]
#######################################

https://git-scm.com/downloads

#######################################
# [[ 2- Configuer Git ]]
#######################################

#>>> Vous pouvez afficher tous vos paramètres et leur origine en utilisant

git config --list --show-origin

# >>> La première chose que vous devez faire lorsque vous installez Git est de 
# définir votre nom d'utilisateur et votre adresse e-mail. Ceci est important
# car chaque commit Git utilise ces informations, et elles sont immuablement 
# intégrées aux commits que vous commencez à créer.

git config --global user.name "John Doe"
git config --global user.email johndoe@example.com

# >>> Si vous souhaitez utiliser un autre éditeur de texte, tel qu'Emacs, vous 
# pouvez procéder comme suit 

git config --global core.editor emacs

# NB: Sur un système Windows, si vous souhaitez utiliser un autre éditeur de texte,
# vous devez spécifier le chemin complet de son fichier exécutable. Cela peut
# être différent selon la façon dont votre éditeur est emballé. 
# ex :git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"

# >>> Pour définir main comme nom de branche par défaut (*), procédez comme suit :

git config --global init.defaultBranch main

#######################################
# [[ 3- Initialiser un projet Git ]]
#######################################

# >>> Créez votre répertoire projet

mkdir mon_projet # ou en mode graphique

# >>> La commande git init crée un nouveau dépôt Git. Elle permet de convertir un
# projet existant, sans version en un dépôt Git ou d'initialiser un nouveau 
# dépôt vide. La plupart des autres commandes Git ne sont pas disponibles hors
# d'un dépôt initialisé, il s'agit donc généralement de la première commande 
# que vous exécuterez dans un nouveau projet.

git init

# # # ETAPE DE CONCEPTION 
# 
#   Ajoutez des fichiers
#   Modifiez des fichers
#   Développez / Codez
#   ...

# >>> La commande git add permet d’ajouter dans la zone de transit les fichiers et dossiers à 
# synchroniser

git add .

# >>> Enregistrez les modifications dans le dépôt local (crée une nouvelle version du projet)

git commit -m 'initial commit of my project'


#######################################
# [[ 3- Travailler avec GitHub ]]
#######################################

# 2 options : 

# opt A) Vous voulez récupérer en local le projet stocké dans un dépot GitHub distant :



# =============================================================================
# [[ EXPORT / IMPORT dconf ]] 
# =============================================================================

# Backup and restore GNOME-specific settings only
dconf dump /org/gnome/ > my_gnome_settings

# Load and restore GNOME-specific settings only
dconf load /org/gnome/ < my_gnome_settings


# =============================================================================
# [[ NODE.JS / NPM ]] 
# =============================================================================

npm init # Create a minimal package.json file

npm install <package name> # Install <package name> locally
npm install -g <package name> # Install <package name> globally
npm install # Install all packages listed in package.json

npm update    # Update local packages to latest version
npm update -g # Update global packages to latest version

npm list    # List locally installed packages
npm list -g # List globally installed packages

# Search the package index for <package name>
npm search <package name>

#######################################################################


…or create a new repository on the command line

echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/970M/test.git
git push -u origin main

…or push an existing repository from the command line

git remote add origin https://github.com/970M/test.git
git branch -M main
git push -u origin main


### 


========================================================================


alias:      Définit des abréviations pour les appels de commandes.
at:         Exécute une commande à un moment précis.
awk (gawk): Implémentation GNU du langage awk permettant le traitement de fichiers.
banner:     Imprime une bannière (sortie de caractères en majuscule ).
basename:   Extrait le nom de fichier d’un chemin d’accès.
bg:         Place un processus en arrière plan.
break:      Termine une boucle.
cal:        Affiche le calendrier.
case:       Structure de contrôle à choix multiples.
cat:        Affiche le contenu d’un fichier.
cd:         Change de répertoire actif.
cfdisk:     Permet de manipuler les partitions
chgrp:      Change l’affectation de groupe pour des fichiers.
chmod:      Change les droits d’accès des fichiers.
chown:      Change le propriétaire d’un fichier.
chroot:     Change le répertoire racine pour l’exécution d’une commande.
cksum:      Affiche le checksum et compte le nombre de byte
clear:      Efface l’écran du terminal
cmp:        Compare deux fichiers.
continue:   Reprend une boucle interrompue avant son terme.
cp:         Copie des fichiers.
cpio:       Copie un fichier d’archive pour la sauvegarde.
crontab:    Exécute des commandes à intervalles réguliers.
cut:        Découpe des morceaux de lignes.
date:       Retourne et règle la date système.
dc:         Desk Calculator
dd:         Copie et convertit des données.
df:         Affiche l’espace disponible sur un support de données.
diff:       Détermine les différences entre les fichiers.
du:         Détermine l’espace disque utilisé.
echo:       Affiche une ligne de texte.
egrep:      Recherche à l’aide d’une expression régulière étendue.
enable:     Active ou désactive les commandes du shell
env:        Modifie l’environnement d’une commande.
eval:       Évalue une commande shell.
exit:       Quitte le shell courant.
expand:     Convertie les tabulations en espaces blancs
export:     Exporte les variables du shell.
expr:       Utilise et calcule des expressions.
false:      Exprime la valeur de retour standard des shelles scripts.
fc:         Rappelle une ligne de commande.
fg:         Place une commande d’arrière-plan au premier plan.
fgrep:      Recherche sans expression réguliere.
file:       Affiche le type de fichier.
find:       Recherche récursivement des fichiers.
for:        Représente une structure de controle.
gcc:        Représente le compilateur C GNU.
grep:       Recherche avec des expressions régulières dans un ou plusieurs fichiers.
history:    Affiche les dernières commandes tapées.
id:         Affiche des identifiants d’utilisateurs et de groupes.
if:         Représente une condition dans un script shell.
jobs:       Affiche des processus d’arrière plan en cours.
join:       Joindre deux fichiers.
kill:       Envoie un signal à un processus.
let:        Affecte arithmétiquement dans le shell.
ln:         Affecte un lien à un fichier.
logname:    Affiche le nom d’utilisateur.
logout:     Déconnecte l’utilisateur
lpq:        Détermine l’état des files d’attentes d’impression.
lpr:        Imprime des fichiers.
lprm:       Annule une requête d’impression.
ls:         Liste les fichiers d’un répertoire.
mail:       Lit et envoie des messages.
man:        Appelle de l’aide en ligne.
mesg:       Fournit des accès aux terminaux.
mkdir:      Créé un répertoire.
mknod:      Créé des fichiers de périphérique et de FIFOs.
more:       Affiche des fichiers et données page par page.
mount:      Affiche la liste des disques montés
mv:         Déplace des fichiers.
newgrp:     Modifie l’appartenance à un groupe.
nice:       Lance une commande avec des priorités modifiés.
nohup:      Ignore les signaux dans le cadre d’une commande.
od:         Affiche des données dans le format interne.
passwd:     Modifie le mot de passe utilisateur.
pg:         Visualise les fichiers et les données page par page.
pr:         Formate des données et des fichiers.
ps:         Affiche des informations sur l’etat des processus en cours.
pwd:        Affiche le répertoire actif.
read:       Lit des valeurs.
readonly:   Protége des variables du shell contre la réécriture.
return:     Retourne une valeur à partir d’une fonction du shell.
rm:         Supprime un fichier.
rmdir:      Supprime un répertoire.
rpm:        Remote Package Manager
sed:        Représente un éditeur de texte batch.
select:     Représente une sélection de menu simple dans le shell.
set:        Fixe des options et des paramètres de position.
shift:      Convertit des paramètres de position.
sleep:      Représente une interruption du traitement pendant un certain temps.
sort:       Trie des données et des fichiers ligne par ligne.
stty:       Configure une interface série.
su:         Change de numéro d’utilisateur.
sync:       Sauvegarde de la mémoire tampon d’entrées/sorties.
tail:       Affiche la fin d’un fichier ou d’un ensemble de données.
tar:        Compresse et archive des fichiers et des répertoires.
tee:        Duplique un flux de données.
test:       Effectue un test sur une condition.
time:       Calcule la durée d’exécution d’une commande.
touch:Modifie la date d’accés ou de modification.
tr:Convertit des caractères.
trap:Gère des réactions aux signaux.
true:Représente la valeur standard pour un shell script.
tty:Affiche le nom des terminaux.
typeset:Modifie les valeurs d’attributs des variables du shell.
ulimit:Fixe la taille maximale d’un fichier.
umask:Définit des droits d’accès prédéfinis.
unalias:Supprime un nom d’alias.
uname:Demande le nom du système.
unset:Supprime des définitions de variables et de fonctions.
until:Représente une structure de contrôle de boucles.
vi:Appelle l’éditeur orienté écran.
wait:Temporise un processus en arrière-plan.
wall:Envoie un message à tous les utilisateurs.
wc:Compte des caractères, des mots et des lignes.
while:Représente une structure de contrôle de boucles.
who:Affiche la liste des utilisateurs connectés.
whoami:Affiche le nom et l’identifiant de l’utilisateur
write:Écrit un message à d’autres utilisateurs.
xargs:Combine des lignes de commandes et de saisie de clavier.
yes:Affiche une chaîne jusqu’à ce qu’il soit interrompu



'970M 9¥©M 9¥ØM 9¥ôM'
'Ruẞï×'
'W012X W®12× W®12¦×'


¥ : altgr+shift+*
© : altgr+c
× : altgr+.
Ø : altgr+shift+s
ô : altgr+o
® : altgr+v
Ð : altrg+shift+h
¦ : altrg+shift+6
ß : altgr+b
ẞ : altrg+shift+b