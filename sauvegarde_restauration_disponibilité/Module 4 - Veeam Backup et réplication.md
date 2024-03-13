# Module 4 - Sauvegarder des machines virtuelles sous Veeam

![alt text](image-16.png)

- **Veeam Backup & Replication** est un logiciel de sauvegarde des données et de reprise d’activité pour les machines virtuelles **VMware vSphere** et **Microsoft Hyper−V**.
- Prise en charge du protocole **VSS** pour la sauvegarde de bases de données Microsoft (protocole de snapshot de Microsoft)
- De nombreuses fonctionnalités de sauvegarde sont prises en charge

>[!IMPORTANT]
**Point faible** : Le protocole de VSS de Microsoft est instable et peut amener des conflits avec le protocole de VSS de Veeam

![alt text](image-17.png)

## Veeam Backup & Replication dans un cadre multi-site

- Rapatrier les sauvegardes de l'ESXi du site B vers le site A par l'intermédiaire du lien WAN.

![alt text](image-18.png)

- Mise en place d'un NAS supplémentaire sur le site et utilisation du serveur Veeam du site A

![alt text](image-19.png)

- On pourrait potentiellement ajouter un serveur Veeam sur le deuxième site,  entraînant par la même occasion un surcoût de licences

![alt text](image-20.png)

![alt text](image-21.png)

## Backup Veeam

- Avant toute chose, il faudra définir les différents supports de stockage dans la  partie Backup Repositories et les assigner.
  - Disques locaux
  - Partages NFS
  - Partages CIFS / SMB
  - Disques durs externes...

- Il est possible de :
  - Sauvegarde l’intégralité des VM
  - Exclure certains disques
  - Choisir le mode de Backup
    - Incremental
    - Reverse Incremental

![alt text](image-22.png)

### Mise en place des Jobs

![alt text](image-23.png)

- La configuration des alertes mail permet d’envoyer des rapports pour les Backups et Réplications (module 08).

![alt text](image-24.png)

> TP4 - Sauvegarde/Restauration avec Veeam