
# Configuration du serveur DHCP sur Windows Server et attribution statique

"" après avoir installée une Vm avec un Iso windows 2012Rd voilà les étapes de ma procédure "" 

![image](https://github.com/manmaryem/Server-Windows-DHCP/assets/137881827/61b61ef6-7583-4353-a3de-0c8773e034ce)


## Procédure
Ouvrez le Gestionnaire de serveurs.
Cliquez sur "Services".
Cliquez sur "Ajouter des rôles et fonctionnalités".
Cliquez sur "Suivant".
Sélectionnez "Installer des rôles et fonctionnalités sur un serveur spécifié".
Cliquez sur "Suivant".
Sélectionnez le serveur sur lequel vous souhaitez installer le rôle DHCP.
Cliquez sur "Suivant".
Dans la boîte de dialogue "Sélectionner des rôles de serveur", sélectionnez "Réseau et services de partage".
Cliquez sur "Suivant".
Dans la boîte de dialogue "Sélectionner des fonctionnalités", cochez la case à côté de "Protocole de configuration d'hôte dynamique (DHCP)".
Cliquez sur "Suivant".
Lisez les conditions d'utilisation et cliquez sur "Accepter".
L'installation du rôle DHCP commencera.
Une fois l'installation terminée, redémarrez le serveur.
Configuration du serveur DHCP
Une fois le serveur redémarré, ouvrez le Gestionnaire DHCP.

![image](https://github.com/manmaryem/Server-Windows-DHCP/assets/137881827/94f0598a-6973-435f-922f-f815acef17ae)

Cliquez sur "Nouvelle étendue".
Dans la boîte de dialogue "Nouvelle étendue", entrez les informations suivantes :
Nom de l'étendue : "Étendue DHCP"
Adresse IPv4 de début : 172.20.0.100
Adresse IPv4 de fin : 172.20.0.200
Masque de sous-réseau : 255.255.255.0
Durée du bail : 1 jour
Cliquez sur "Suivant".
Dans la boîte de dialogue "Options d'étendue", cochez les cases à côté des options suivantes :
Adresse IP
Serveur DNS
Serveur WINS (facultatif)
Cliquez sur "Suivant".
Dans la boîte de dialogue "Réservations", cliquez sur "Nouvelle réservation".
Dans la boîte de dialogue "Nouvelle réservation", entrez les informations suivantes :
Nom de la réservation : "Ordinateur client"
Adresse MAC du client : 00-00-00-00-00-00
Adresse IPv4 : 172.20.0.10

![image](https://github.com/manmaryem/Server-Windows-DHCP/assets/137881827/05bf0adb-496f-4f22-bbb5-1445929a1bf4)

Cliquez sur "Suivant".
Dans la boîte de dialogue "Réservations", cliquez sur "Terminer".
Test de la configuration DHCP
Démarrez un nouvel ordinateur client.
Attendez que l'ordinateur client reçoive une adresse IP du serveur DHCP.
Ouvrez la fenêtre "Propriétés réseau" de l'ordinateur client.
Cliquez sur l'onglet "Internet Protocol Version 4 (TCP/IPv4)".
Cliquez sur le bouton "Propriétés".
Vérifiez que l'adresse IP, le masque de sous-réseau, la passerelle par défaut et le serveur DNS sont correctement configurés.

![image](https://github.com/manmaryem/Server-Windows-DHCP/assets/137881827/1990fa5d-9cda-4c8a-8094-a860c6b2d112)

Le client qui possède la réservation n'obtient pas une autre IPv4, même si il demande un renouvellement.

![image](https://github.com/manmaryem/Server-Windows-DHCP/assets/137881827/7d331d6f-701c-4803-9666-e451dca93ffd)


