# Infrastructure Active Directory — Windows Server 2022

Déploiement d'une infrastructure Windows Server 2022 complète pour une entreprise fictive (domaine `axeplane.loc`) : Active Directory, DNS, DHCP, stratégies de groupe, partages et gestion des droits.

Projet de formation réalisé dans le cadre du titre professionnel TSSR.

## Environnement

| Élément | Détail |
| --- | --- |
| Serveur | Windows Server 2022, 2 disques (système + données sur `E:`) |
| Client | Windows 10/11 Entreprise |
| Domaine | `axeplane.loc`, nouvelle forêt |
| Réseau | Réseau privé hôte, IP fixe sur le serveur, DHCP pour les clients |
| Virtualisation | VirtualBox |

## Ce qui a été mis en place

### Serveur de domaine (SRVAD)

- Installation de Windows Server 2022, configuration réseau (IP fixe, passerelle, DNS), renommage du serveur
- Initialisation du second disque et montage sur `E:` pour les données
- Installation des rôles **AD DS**, **DNS** et **DHCP**
- Promotion en contrôleur de domaine, création de la forêt `axeplane.loc`

### Services réseau

- Création de l'étendue DHCP
- Zone de recherche inversée DNS et enregistrements **A**, **PTR** et **CNAME**

### Annuaire et droits

- Unités d'organisation et groupes de sécurité reflétant la structure de l'entreprise
- Comptes utilisateurs de test
- Dossiers partagés avec attribution des droits selon la méthode **AGDLP** (Account → Global → Domain Local → Permission)

### Postes clients

- Installation de Windows 10/11 Entreprise sur une VM cliente
- Vérification de la chaîne DHCP → DNS → accès Internet, puis intégration au domaine
- Connexion avec les comptes de domaine et contrôle du mappage automatique du lecteur `P:`
- Test de l'isolation des dossiers personnels entre utilisateurs

### Stratégies de groupe

| GPO | Effet |
| --- | --- |
| Mappage de lecteurs réseau | Lecteurs montés selon le groupe de sécurité de l'utilisateur |
| Désactivation du Microsoft Store | Restriction du poste de travail |
| Déploiement d'OpenVPN | Installation automatique du client (sans profil) pour les services Informatique et Commercial |

## Compétences mises en œuvre

Active Directory · DNS · DHCP · GPO · droits NTFS et méthode AGDLP · partages réseau · intégration de postes au domaine · virtualisation

## Note

Les machines virtuelles de ce projet ne sont pas distribuées ici : les exports dépassent largement la limite de taille de GitHub. Le dépôt documente la démarche et la configuration.
