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
    ```bash
    modinfo NOM_MODULE

- Charger/décharger un module :
    ```bash
    sudo modprobe NOM_MODULE  # charger
    sudo modprobe -r NOM_MODULE  # décharger

- Messages émis par les pilotes :
    ```bash
    dmesg | grep NOM_MODULE


## MS Windows

- WSL (Windows Subsystem for Linux) permet de lancer un environnement Linux sur Windows.
- Permet d'exécuter des binaires Linux sans machine virtuelle.
- Utilise un protocole interne pour traduire appels système Linux vers le noyau Windows.

## Sécurisation SSH

- Modifier `/etc/ssh/sshd_config` pour :
  - Interdire root login
  - Utiliser clés SSH plutôt que mot de passe 
  - Limiter les utilisateurs autorisés 

## Alerte clé publique SSH

- Supprimer l'entrée existante dans `~/.ssh/known_hosts` ou utiliser :
  ```bash
  ssh-keygen -R hostname


## Oh les gourmands

- Identifier en une seule commande :
  ```bash
  du -sh /home/* | sort -hr | head -n 10



## Préparer un système pour développement

### Debian / Ubuntu

    sudo apt update
    sudo apt install build-essential git gcc gdb make

### Red Hat / Fedora
    sudo dnf groupinstall "Development Tools"
    sudo dnf install git gcc gdb make


---

## Connexions utilisateurs et sudo

## Qui fait quoi ?

- Dernières connexions : 
  ```bash
  last
  last -a



