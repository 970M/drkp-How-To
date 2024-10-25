# Ubuntu kernel updates

[README.md](README.md)


## Installation de Modules additionnels du noyau

Si vous utilisez une version spécifique du noyau (dans ce cas, 5.13.0-21), et que vous avez besoin de modules additionnels pour prendre en charge du matériel ou des fonctionnalités spécifiques, cette commande les installe.

```
sudo apt install linux-modules-extra-5.13.0-21-generic
```


## Mise à jour linux-headers

Si tu as mis à jour vers Ubuntu 22.04 mais que tu remarques que le paquet des linux-headers n'est pas mis à jour vers la dernière version disponible, voici les étapes à suivre pour résoudre le problème.

1. Vérifier la version courante des headers et du noyau
D'abord, vérifie la version actuelle de ton noyau et des linux-headers :
```
uname -r
dpkg -l | grep linux-headers
```
Cela te permettra de voir quelle version du noyau est actuellement installée et si les headers sont bien synchronisés.

2. Mettre à jour la liste des paquets
Ensuite, assure-toi que tous les paquets sont bien mis à jour et que la liste est à jour.
```
sudo apt update
sudo apt upgrade
```
3. Installer manuellement les headers manquants
Si le noyau est déjà à jour mais pas les headers, tu peux essayer d’installer manuellement la version correspondante. Par exemple :
```
sudo apt install linux-headers-$(uname -r)
```
Cela installera les headers correspondant exactement à la version de ton noyau en cours.

4. Mettre à jour tous les noyaux et headers
Si tu veux être sûr que tous les noyaux et leurs headers sont mis à jour, utilise cette commande :
```
sudo apt install --install-recommends linux-generic
```
Cette commande installe non seulement le noyau le plus récent, mais aussi ses headers et dépendances.

5. Redémarrer le système
Après avoir mis à jour le noyau et les linux-headers, il est recommandé de redémarrer ton système pour utiliser la dernière version du noyau et des headers :
```
sudo reboot
```
Après le redémarrage, vérifie à nouveau la version avec uname -r et assure-toi que tout est en ordre.

6. Résolution des problèmes
Si malgré tout cela tu rencontres encore des soucis, il peut être utile de vérifier s'il y a des dépendances cassées ou des paquets en conflit :
```
sudo apt --fix-broken install
sudo apt autoremove
```

## Mettre à jour linux-headers-generic-hwe-20.04 pour ubuntu 22.04

Étape 1 : Vérifier le noyau actuellement utilisé
Tout d'abord, il faut vérifier quelle version du noyau est en cours d'exécution.
```
uname -r
```
Cela te donnera la version du noyau actuellement utilisée. Si c'est une version qui correspond à Ubuntu 20.04 (comme un noyau 5.4.x), c'est un signe qu'il n'a pas été mis à jour vers la version attendue pour Ubuntu 22.04 (comme un noyau 5.15.x ou ultérieur).

Étape 2 : Installer le noyau générique d'Ubuntu 22.04
Ensuite, installe les linux-headers-generic et le noyau HWE (Hardware Enablement Stack) correspondant à Ubuntu 22.04 :
```
sudo apt update
sudo apt install --install-recommends linux-generic-hwe-22.04
```
Cela installera la version correcte du noyau et des headers pour Ubuntu 22.04.

Étape 3 : Supprimer les anciens paquets HWE 20.04
Une fois que tu as mis à jour le noyau, tu peux supprimer les anciens paquets qui correspondent à la version 20.04 pour éviter des conflits à l'avenir :
```
sudo apt remove linux-headers-generic-hwe-20.04 linux-image-generic-hwe-20.04
```

Étape 4 : Redémarrer le système
Après avoir mis à jour le noyau et supprimé les anciens paquets, redémarre ton système pour charger le nouveau noyau :
```
sudo reboot
```

Étape 5 : Vérifier à nouveau la version du noyau
Après le redémarrage, vérifie que tu utilises maintenant le bon noyau avec la commande :
```
uname -r
```

## Nettoyer /boot

### Taille du répertoire /boot

```
df | grep /boot
```

### Dernière image kernel active

```
uname -a
uname -r
```

### Liste les images linux présentes

```
sudo dpkg --list 'linux-image*'
sudo dpkg -l | grep -Ei "linux-headers|linux-image"
sudo dpkg --list 'linux-image*'|awk '{ if ($1=="ii") print $2}'|grep -v `uname -r`
```

```
dpkg -l | awk '!/^rc/ && / linux-(c|g|h|i|lo|m|si|t)/{print $1,$2,$3,$4 | "sort -k3 | column -t"}'
```

### Information sur le packet

```
apt show linux-image-generic-hwe-20.04
apt search linux-image-generic
```
 
### Supprimer les images inutilisées
```
sudo apt-get remove linux-headers-5.8.0-55-generic linux-image-5.8.0-55-generic
sudo apt-get autoremove
sudo update-grub
```
 
