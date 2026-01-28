# TP 2 - LINUX B1

## I. Exploration locale en solo

### 1. Affichage d'informations sur la pile TCP/IP locale

### En ligne de commande : 

#### **Interface WIFI** :

commande = `ifconfig en0`

![alt text](image.png)

- Nom de l'interface : `en0`

- Adresse MAC (ether) : `56:97:6d:0b:27:44`

- Adresse IP (inet) : `10.33.68.116`

- Adresse de Broadcast : `10.33.79.255`

- Adresse de Réseau : `10.33.64.0`

#### **Interface ETHERNET** (Non applicable MacBook Air sans port Ethernet ni adaptateur branché) : 


#### **AFFICHER GATEWAY**

Commande = `route get default | grep gateway`

- gateway = `10.33.79.254`

![alt text](image-2.png)

### En graphique (GUI : Graphical User Interface)

![alt text](image-3.png)

![alt text](image-4.png)

### **Questions** : à quoi sert la gateway dans le réseau d'Ingésup ?

- Dans le réseau d'Ingésup, la gateway sert à sortir du réseau local pour accéder à d'autres réseaux, et principalement à Internet.

### 2. Modifications des informations

Adresse IP actuel : `10.33.68.116`

Première IP disponible : `10.33.64.1`

Dernière IP disponible : `10.33.79.254`

#### **A. Modification d'adresse IP - pt. 1** : 

![alt text](image-5.png)

![alt text](image-6.png)

#### **B. nmap**

Commande = `nmap -sP 192.168.1.0/24`

![alt text](image-7.png)

#### **C. Modification d'adresse IP - pt. 2**

Adresse libre + modification gateway :

![](image-9.png)

![alt text](image-8.png)

### **III. Manipulations d'autres outils/protocoles côté client**

Commande pour voir les détails cachés du DHCP : `ipconfig getpacket en0` 

Adresse IP du serveur DHCP : `10.33.79.254``

Durée du bail (DHCP Lease) : `0x866c`

Conversion : 0x866c en décimal = `34 412 secondes`

En heures : 34412 / 3600 ≈ 9,5 heures (environ 9h30). Le bail dure environ 9h30. L'expiration sera donc `(heure actuelle) + 9h30.``

Renouvellement de l'IP : `sudo ipconfig set en0 DHCP`



