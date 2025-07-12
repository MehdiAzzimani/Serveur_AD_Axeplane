# Serveur_AD_Axeplane

Mdp: 
- admin : Blabla02
- Mehdi:  Blabla01
  
(Mode d'accés réseau des 2 vm en réseau privé hôte) 

 Projet : Mise en place d'une infrastructure Active Directory sur Windows Server 2022

Ce projet a pour objectif de déployer une infrastructure Windows Server 2022 avec Active Directory, DNS, DHCP, stratégies de groupe (GPO) et gestion des utilisateurs, dans un environnement de type entreprise.
   Étapes principales du projet

    Préparation du serveur AD (SRVAD)

        Installation de Windows Server 2022 sur une VM avec 2 disques.

        Configuration réseau (IP fixe, passerelle, DNS), renommage du serveur.

        Initialisation du second disque et attribution de la lettre E.

    Installation et configuration des rôles

        Installation des rôles AD DS, DNS et DHCP.

        Création d’un domaine dans une nouvelle forêt : axeplane.loc.

        Création de l’étendue DHCP, zone de recherche inversée, et enregistrements DNS (A, PTR, CNAME).

        Création des UO et des groupes de sécurité.

        Création des comptes utilisateurs de test.

        Création des dossiers partagés et configuration des droits d’accès selon la méthode AGDLP.

    Préparation des postes clients

        Installation de Windows 10/11 Entreprise sur une VM Client Test.

        Vérification du DHCP, DNS, accès Internet, et intégration au domaine.

        Connexion avec les comptes de domaine et test du mappage automatique du lecteur P.

        Test de l'isolation des dossiers personnels entre utilisateurs.

    Mise en place de GPO

        GPO de mappage de lecteurs réseau selon les groupes de sécurité.

        GPO pour désactiver le Microsoft Store.

        GPO de déploiement automatique d’OpenVPN (sans profil) pour les services Informatique et Commercial.
