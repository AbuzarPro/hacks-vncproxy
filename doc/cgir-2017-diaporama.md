% Administration à distance à travers un proxy HTTP/HTTPS
% Fatemeh Zohari ; Florian Legrand ; Jean Canivez
% 30 Mars 2017


# Introduction

## Objectif
- Prendre le contrôle la machine(réseau privé) dériére un proxy web à partir une machine(adresse publique)
- La machine à assister peut fonctionner sous Linux, Windows ou Mac.
- Outils sous licence libre
- Données circulent chiffrées
- Le plus simple possible (accessible à un non-informaticien) 


# VNC

## VNC = Virtual Network Computing

![](img/vnc-exemple.jpg)

- Fonctionnement
    - Client qui écoute
    - Serveur diffuse son écran
- Flux de données
    - Protocole spécifique VNC
    - Au dessus d'un canal SSH

## Reverse VNC

Inverser rôle serveur/client
- Client attend
- Serveur se connecte

Outils

- Côté client : xtightvncviewer
- Côté serveur : x11vnc/TightVNC

Linux > Linux

- Client : `xvnc4viewer -listen`
- Serveur : `x11vnc -connect 172.18.48.231:5500`

Windows > Linux

- Client Linux : `xvncviewer -listen`
- Serveur Windows : TightVNC


# Proxy HTTP/HTTPS

## Problèmes

- Seul communication possible
    - Du serveur vers le client
    - HTTP ou HTTPS
    - Via un proxy
- Contraintes
    - Communication doit être chiffrée

**Faire passer flux SSH au dessus d'un proxy HTTP/HTTPS**


## Solutions

Outils
- Choix de Corksrew

Avantage
- Facilité d'installation et de configuration

Inconvénients
- Besoin d'une redirection de port 

Configuration
- Modification du fichier `.ssh/config`
- Rédaction de script

## Aspects pratiques

### LINUX vers LINUX

- Installation et configuration de Corkscrew
- Via deux choix possible : Manuellement ou via un script
- Choix de la méthode via un script d'éxécution (gain de productivité et accessibilité)

### WINDOWS vers LINUX

- Installation Cygwin et Corkscrew
- Mêmes cas et choix que pour Linux


# Résultat

## Principe général

![](img/vnc-ssh.png)

## Procédure

![](img/recapitulatif.png)

# Conclusion

## Conclusion

- Prendre le contrôle d'un pc à distance situé derrière un proxy

- Découverte de nouveaux outils de collaboration et d'administration

- Gain en capacités

Remerciements

- A Mr Beaufils et Mr Peter
- Les administrateurs de l'IUT pour le prêt de matériel 
- Thibeuf Antoine pour la finalisation de diaporama


