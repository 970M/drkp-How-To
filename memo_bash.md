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

## Grep

### Rechercher des fichiers contenant EXPR

```
grep -ril EXPR ./
```


## Find
```
find . -name '*.jpg' -print | awk -F'/' '{print $3 $2}'
```


## Permissions / Groupe

### Afficher la liste des utilisateurs :

```
cat /etc/passwd | awk -F: '{print $ 1}'
```

### Afficher la liste des groupes
```
cat /etc/group | awk -F: '{print $ 1}'
```

### Liste les membre d'un groupe
```
getent group groupname 
cat /etc/group
```

### Les droits sont drwxrwx— (770) pour les répertoires et -rwxrwx—- (770) pour les fichiers :
```
chmod -R 770 monrep
```
### drwxrwx— (770) pour les répertoires et -rw-rw—- (660) pour les fichiers : 
```
chmod -R u-x,g-x,u+X,g+X monrep
sudo chmod 0750 
```
## Logigiels

### Logiciel installés

```
ls /usr/share/applications | awk -F '.desktop' ' { print $1}'
```
```
dpkg --list
snap list
apt list --installed
```

### Supprimer programme
```
sudo apt-get --purge remove program
```

## Ecrire en couleur
```
echo -e "[\033[35m$USER\033[30m@\033[32m$HOSTNAME\033[30m:\033[31m$PWD\033[30m]$ "
```


## Export / Import dconf ]] 

### Backup and restore GNOME-specific settings only
```
dconf dump /org/gnome/ > my_gnome_settings
```

#### Load and restore GNOME-specific settings only
```
dconf load /org/gnome/ < my_gnome_settings
```


## Node.js / nmp 
```
npm init # Create a minimal package.json file

npm install <package name> # Install <package name> locally
npm install -g <package name> # Install <package name> globally
npm install # Install all packages listed in package.json

npm update    # Update local packages to latest version
npm update -g # Update global packages to latest version

npm list    # List locally installed packages
npm list -g # List globally installed packages
```
### Search the package index for <package name>
```
npm search <package name>
```
