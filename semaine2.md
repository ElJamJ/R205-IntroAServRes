### Résumé des points clés de la configuration des paramètres réseau avec Linux

#### Méthode volatile
1. **Commandes principales utilisant `ip`**:
   - `ip address add` : Configurer une interface réseau.
   - `ip address del` : Déconfigurer une interface réseau.
   - `ip address show` : Vérifier la configuration réseau.
   - `ip link show` : Vérifier l’état d’une interface réseau.
   - `ip link set` : Activer/désactiver une interface réseau.

#### Méthode pérenne
1. **Fichier de configuration** :
   - **Emplacement** : `/etc/network/interfaces`.
   - **Étapes** :
     - Arrêter le service réseau avant toute modification.
     - Ajouter une section par interface.
     - Chaque ligne correspond à un paramètre de configuration.

2. **Paramètres de configuration** :
   - `auto ethX` : Activer l'interface au démarrage.
   - `allow-hotplug ethX` : Activer l'interface dès la présence de liaison.
   - `iface ethX inet static` : Configuration statique de l'interface.
   - `address a.b.c.d` : L'adresse IPv4 de l'interface.
   - `netmask w.x.y.z` : Le masque de sous-réseau.
   - `gateway j.k.l.m` : La passerelle par défaut.

3. **Exemple de configuration** :
   - Nom de l’interface : `eth0`.
   - Adresse IP : `192.168.0.200`.
   - Masque de sous-réseau : `255.255.255.240` (notation CIDR : `/28`).

4. **Calcul de l'adresse réseau** :
   - Adresse IP : `192.168.0.200`.
   - Masque de sous-réseau : `255.255.255.240`.
   - Adresse réseau calculée : `192.168.0.192`.
   - Adresse de broadcast : `192.168.0.207`.

#### Commandes pour gérer les services réseau
1. **Arrêter le service réseau** :
   - Commande : `service networking stop`.

2. **Lire et modifier le fichier de configuration** :
   - `cat /etc/network/interfaces` : Afficher le contenu du fichier.
   - `ls /etc/network/interfaces.d` : Lister les fichiers dans le répertoire.

### Points supplémentaires
- Seul le super-utilisateur `root` peut réaliser les configurations réseau.
- Utilisation des pages de manuel (`man`) pour les commandes et fichiers de configuration.

Ces points couvrent les principales commandes et étapes pour configurer les paramètres réseau sur une machine Linux en utilisant les méthodes volatile et pérenne.
