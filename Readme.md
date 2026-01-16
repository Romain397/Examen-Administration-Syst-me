# Examen Administration Système - 16 janvier 2026

## Les deux familles

### Principales distributions

- **Famille Debian :**
  - Debian, Ubuntu, Linux Mint
- **Famille Red Hat :**
  - Red Hat Enterprise Linux (RHEL), CentOS Stream, Fedora
- **Autres :**
  - Arch Linux, Gentoo, Alpine Linux, SUSE

### Positionnement et outils d'administration

- **Debian / Ubuntu :**
  - Gestion de paquets : `apt`, `dpkg`
  - Configuration simple, communauté large
- **Red Hat / CentOS / Fedora :**
  - Gestion de paquets : `yum`, `dnf`, `rpm`
  - Orientation entreprise, support commercial RHEL
- **Différences clés :**
  - Outils de paquet différents
  - Fichiers de configuration parfois différents (`/etc/apt/` vs `/etc/yum/`)

## Back to basics

- **Mode kernel/superviseur :** 
  - Accès direct au matériel, exécution d’instructions privilégiées, gère la mémoire, pilotes, processus.
- **Mode utilisateur :**
  - Applications normales, accès limité, passent par appels système pour utiliser le hardware.

## Qui est où ?

- `/etc` : fichiers de configuration du système
- `/bin` et `/usr/bin` : commandes binaires accessibles à tous
- `/sbin` et `/usr/sbin` : commandes administratives
- `/home` : répertoires personnels des utilisateurs
- `/var` : fichiers variables (logs, bases, cache)
- `/var/log` : fichiers journaux
- `/var/lib` : données persistantes des applications (ex: bases locales)

## Où est le pilote ?

- Liste des pilotes chargés : 
  ```bash
  lsmod

- Fichiers binaires des modules :

modinfo NOM_MODULE

- Charger/décharger un module :

sudo modprobe NOM_MODULE  # charger
sudo modprobe -r NOM_MODULE  # décharger

- Messages émis par les pilotes :

dmesg | grep NOM_MODULE