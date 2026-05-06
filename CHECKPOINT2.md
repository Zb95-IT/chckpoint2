# CHECKPOINT 2 — Fichier réponses

---

## Exercice 1 — Théorie sur infrastructure client/serveur

### Q.1.1

**Point de vue serveur :**
Le serveur est correctement configuré.

**Point de vue client :**
Le problème vient du client : il a une IP statique, d'où le non-fonctionnement du DHCP.

### Q.1.2

Ça ne ping pas car ils n'appartiennent pas au même réseau.

### Q.1.3

Il y a une exclusion des adresses IP de `172.16.10.1` à `172.16.10.19`.

### Q.1.4

On définit un scope/réservation dans notre serveur DHCP.

### Q.1.5

`fe80::80f:5482:53ea:7644%6`

### Q.1.6

Autres types d'adresse IPv6 :

| Nom | Préfixe | Portée |
|-----|---------|--------|
|     |         |        |

### Q.1.7

Oui, il va avoir une adresse IPv6.

### Q.1.8

Le DNS permet ça.

### Q.1.9

Car c'est le plus moderne et les OS mettent ça en avant automatiquement.

### Q.1.10

Il faut configurer ça dans le DNS pour qu'il fasse la traduction.

---

## Exercice 2 — Théorie sur réseau IP

### Q.2.1

**Matériel A et B :**
A et B = switches, couche 2 du modèle OSI.
Rôle : faire communiquer des machines grâce à l'adresse MAC.

### Q.2.2

| PC  | Adresse réseau | 1ère adresse disponible | Dernière adresse disponible | Adresse de diffusion |
|-----|---------------|------------------------|-----------------------------|---------------------|
| PC1 | 10.10.0.0     | 10.10.0.1              | 10.10.255.254               | 10.10.255.255       |
| PC2 | 10.11.0.0     | 10.11.0.1              | 10.11.255.254               | 10.11.255.255       |
| PC3 | 10.10.0.0     | 10.10.0.1              | 10.10.255.254               | 10.10.255.255       |
| PC4 | 10.10.0.0     | 10.10.0.1              | 10.10.255.254               | 10.10.255.255       |
| PC5 | 10.10.0.0     | 10.10.0.1              | 10.10.255.254               | 10.10.255.255       |

### Q.2.3

**Rôle de A pour un ping de PC1 vers PC3 :**
Il redirige correctement la trame Ethernet via l'adresse MAC pour les faire communiquer ensemble. Ils sont dans le même réseau.

**Communication réussie ?** Oui.

### Q.2.4

**Ping de PC5 vers PC2 :**
PC5 ne reçoit pas de réponse car PC2 ne peut pas communiquer avec lui. PC5 peut communiquer avec le réseau `10.10.x.x` mais PC2 ne peut pas communiquer avec le réseau `10.11.x.x`.

### Q.2.5

**Ping de PC2 vers PC5 :**
PC2 ne peut pas communiquer avec PC5 car il n'y a pas de passerelle entre eux et ils n'appartiennent pas au même réseau.

### Q.2.6

**Matériel C et D :**
Ce sont des routeurs. Leur but est de servir de passerelle pour aller sur Internet. Ils sont sur la couche 3 du modèle OSI.

### Q.2.7

**Ping de PC1 vers g2/0 de D :**
Le rôle de D est de router le paquet IP vers Internet. Oui, la communication fonctionne.

### Q.2.8

**Rôle de la passerelle de PC3 :**
Non, elle fait son rôle pour tous sauf PC2.

### Q.2.9

**Pour le matériel C, label `g1/0` :**
- **g** = GigabitEthernet
- **1** = Slot 1
- **0** = Port 0

### Q.2.10

**Périmètre de la commande :**
On configure ça au niveau de la table de routage, donc sur le routeur.

### Q.2.11

| Emplacement sur le réseau | Adresse MAC destination | Adresse MAC source | @IP Source | @IP Destination |
|--------------------------|------------------------|-------------------|------------|-----------------|
| Entre PC1 et A           | CA:01:DA:D2:00:08      | 00:50:79:66:68:00 | 10.10.4.1  | 172.16.5.0/24   |
| Entre B et C             | CA:01:DA:D2:00:08      | 00:50:79:66:68:00 | 10.10.4.1  | 172.16.5.0/24   |
| Entre C et D             | CA:03:9E:EF:00:38      | CA:01:DA:D2:00:1C | 10.10.4.1  | 172.16.5.0/24   |
| Après D                  | ?????                  | CA:03:9E:EF:00:54 | 10.10.4.1  | 172.16.5.0/24   |

### Q.2.12

**Table de routage de C :**

| Réseau de destination | Masque (CIDR) | Adresse de passerelle | Adresse de sortie |
|----------------------|---------------|----------------------|-------------------|
|                      |               |                      |                   |
-------------------------------------------------
# A PARTIR DICI JE NAI PAS REPONDU
-------------------------------------------------
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
## Exercice 3 — Pratique sur infrastructure client/serveur

### Q.3.1
> Copie d'écran d'un ping du serveur vers le client en IPv4.

### Q.3.2
> Copie d'écran du résultat de la commande `ipconfig /all` sur le client.

### Q.3.3
> Copie d'écran d'un ping du serveur vers le client en IPv4.

### Q.3.4
> Copie d'écran des commandes CLI + `ipconfig /all`.

### Q.3.5
> Copie d'écran d'un ping du serveur vers le client en IPv4.

---

### Actions sur le serveur

### Q.3.6
> Copie d'écran du changement de configuration.

### Q.3.7
> Copie d'écran du résultat de `ipconfig /all` sur le client.

### Q.3.8
> Copie d'écran de la configuration modifiée sur le serveur.

### Q.3.9
> Copie d'écran du résultat de `ipconfig /all` sur le client.

### Q.3.10
> Copie d'écran d'un ping depuis le serveur vers le client en IPv6.

### Q.3.11
> Copie d'écran de la configuration DHCPv6 sur le serveur.

### Q.3.12
> Copie d'écran d'un ping du client vers le serveur avec le nom du serveur (IP de sortie en v4).

### Q.3.13
> Copie d'écran des modifications de configuration serveur et client + ping vers CLIENT_TEST.

---

## Exercice 4 — Pratique sur réseau IP

### FICHIER FILE1

**Q.4.1** — Ethertype du protocole encapsulé ? Nom et rôle du protocole encapsulé ?

**Q.4.2** — Utilité de la communication ?

**Q.4.3** — Nom du matériel répondant ? Justification ?

**Q.4.4** — Emplacement de la capture ? Justification ?

### FICHIER FILE2

**Q.4.5** — Protocoles encapsulés ?

**Q.4.6** — Matériel source ? Matériel destination ?

**Q.4.7** — Réussite de la communication (justification) ?

**Q.4.8** — Emplacement de la capture ? Justification ?

### FICHIER FILE3

**Q.4.9** — Détails de la capture.

**Q.4.10** — Réussite de la communication (justification) ?

**Q.4.11** — Capture entre C et D ? Justification ?

---

## Exercice 5 — Débogage de script PowerShell

### Q.5.1
> Copies d'écran de la configuration pour le partage de dossier.

### Q.5.2
> Copie d'écran de la modification du code pour que `AddLocalUsers.ps1` s'exécute correctement.

### Q.5.3
> Copie d'écran du commentaire avec la modification du code + résultat.

### Q.5.4
> Copie d'écran du commentaire avec la modification du code + résultat.

### Q.5.5
> Copie d'écran du commentaire avec la modification du code.

### Q.5.6
> Copie d'écran du commentaire avec la modification du code + résultat.

### Q.5.7
> Copie d'écran du commentaire avec la modification du code.

### Q.5.8
> Copie d'écran du commentaire avec la modification du code.

### Q.5.9
> Copie d'écran du commentaire avec la modification du code + résultat.

### Q.5.10
> Copie d'écran du commentaire avec la modification du code.

### Q.5.11
> Copie d'écran du commentaire avec la modification du code.
