---
description: Pour lancer le processus d’intégration d’Adobe Data Workbench (DWB), composant d’Adobe Analytics Premium (AAP), procédez comme suit.
title: Instructions d’intégration de base pour les services gérés DWB
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Instructions d’intégration de base pour les services gérés DWB{#basic-onboarding-instructions-for-dwb-managed-services}

Pour lancer le processus d’intégration d’Adobe Data Workbench (DWB), composant d’Adobe Analytics Premium (AAP), procédez comme suit.

Ces instructions d’intégration sont destinées aux clients qui implémentent les outils de données avec une seule suite de rapports à l’aide des services gérés Adobe sans consulter les services de conseil. Si vous êtes un nouveau client AAP qui met en oeuvre DWB, l’équipe d’intégration d’Adobe sera votre premier contact. Si vous effectuez une mise à niveau à partir de la norme Adobe Analytics ou d’une version antérieure de DWB, un responsable de succès client Adobe vous aidera.

## Infos d&#39;intégration : Ce dont nous avons besoin de vous {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe vous contactera pour :

* Identifiez un utilisateur principal pour DWB afin de générer un certificat spécifique pour cet utilisateur dans le répertoire réseau. L’utilisateur principal agira également comme personne de contact pour interagir avec le service à la clientèle d’Adobe.
* Identifiez la suite de rapports à charger dans DWB.

Les équipes Adobe Digital Marketing saisiront ensuite vos informations pour créer des profils, définir des comptes et diffuser un fichier de configuration pour DWB.

**Tâches d’intégration Adobe**

* Le service à la clientèle Adobe crée un compte sous licence DWB. Le service à la clientèle d’Adobe génère un certificat DWB pour l’utilisateur principal.
* Le service à la clientèle d’Adobe définit l’utilisateur principal comme un &quot;utilisateur pris en charge&quot;, la personne identifiée pour les appels pris en charge et la résolution des problèmes.
* Le service à la clientèle Adobe charge le pack logiciel sur le portail de licences et de logiciels DWB (profil SoftDocs/Software and Docs) à télécharger dans votre entreprise.
* L’équipe TechOps d’Adobe prépare les environnements de production et de développement et leurs profils (par contrat) pour DWB.
* L’équipe TechOps d’Adobe configure les flux de données et les scripts de gestion des profils.
* L’équipe TechOps d’Adobe crée et envoie le fichier de configuration DWB (Insight.cfg) à l’équipe d’intégration Adobe responsable des tâches d’intégration associées à votre entreprise.

Après avoir personnalisé vos flux de données et généré des informations d’identification, des certificats et une configuration de profil, le service à la clientèle Adobe enverra votre fichier de configuration et vos informations d’identification pour passer à l’étape suivante.

## Accès à vos fichiers d’installation personnalisés {#section-26962bf57fef435dbd1c5486d4b6f688}

Vous recevrez ces fichiers de configuration du service à la clientèle d’Adobe pour installer DWB Workstation sur votre ordinateur client.

* Votre fichier de configuration DWB personnalisé (Insight.cfg)

   Ce fichier de configuration sur l’ordinateur client inclut des connexions à vos serveurs DWB gérés.

* Identifiants de connexion pour le portail de licences afin de télécharger l’assistant de configuration DWB et le certificat requis (fichier .pem) avec le nom de votre utilisateur principal.

**Téléchargement de fichiers de configuration supplémentaires**

1. Accédez à : license.visualsciences.com pour télécharger votre certificat de licence et le fichier exécutable de l’Assistant Installation DWB.
1. Entrez votre organisation (nom du compte), le nom de l’utilisateur principal et le mot de passe que vous avez reçu du service à la clientèle Adobe, puis cliquez sur Se connecter.

   >[!NOTE]
   >
   >Votre navigateur peut vous inviter à présenter un certificat numérique à ce stade. Si tel est le cas, cliquez sur Annuler pour fermer la boîte de dialogue.

1. Recherchez le certificat émis pour votre instance d’Adobe Data Workbench (`<PrimaryUser>`.pem) dans la section Téléchargements et téléchargez-le.
1. Localisez le programme d’installation du client Standard dans la section Téléchargements pour télécharger l’Assistant Installation de DWB (InsightSetup-x.xx.exe fichier).
1. Après avoir reçu et téléchargé des fichiers du service à la clientèle d’Adobe, exécutez l’assistant de configuration DWB pour installer le logiciel de la station de travail sur votre ordinateur client.

>[!NOTE]
L’assistant de configuration DWB vous guidera tout au long de l’installation de la station de travail cliente DWB et vous aidera à localiser les fichiers Insight.cfg et `<PrimaryUser>`.pem à placer dans les dossiers requis. Le fichier Insight.cfg réside dans le fichier Insight.exe de votre station de travail client installée. Le fichier `<PrimaryUser>`.pem réside dans le dossier Certificates avec le fichier trust_ca_cert.pem. Tous les fichiers de certificat et de configuration doivent être présents pour que DWB fonctionne.

Pour plus d’informations, voir l’Assistant [de configuration](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html)DWB.

## Connexion à vos serveurs DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Vos serveurs gérés sont identifiés dans le fichier Insight.cfg que vous recevez du service à la clientèle d’Adobe et que vous résidez sur votre poste de travail client. Adobe TechOps configurera vos serveurs et le service à la clientèle d’Adobe ajoutera des références à ces serveurs et profils gérés dans le fichier Insight.cfg avant de vous l’envoyer. (La configuration des connexions au serveur à l’étape 12 de la documentation de l’Assistant Installation DWB sera terminée.)

>[!NOTE]
Dans l’espace de travail Configuration de la station de travail sur la station de travail cliente DWB, vous pourrez voir vos serveurs et profils connectés.

**Adobe Managed Services**

・ Adobe TechOps gère l’infrastructure, y compris le réseau, le centre de données, les serveurs et le stockage. La surveillance de l&#39;infrastructure et la réponse aux alertes surviennent 24h/24 et 7j/7 pour les alertes nécessitant une action TechOps. Pour d’autres alertes, TechOps avertit le service à la clientèle Adobe de se coordonner avec vous.

・ Adobe TechOps effectuera des mises à jour de maintenance et de microprogramme pour vos serveurs gérés. En cas d’interruption de maintenance, vous recevrez au moins deux semaines à l’avance des notifications de fenêtre de maintenance de la part du service à la clientèle. Adobe TechOps répond aux besoins immédiats le plus rapidement possible. La notification dépendra de l&#39;urgence et sera résolue une fois le calendrier connu.

・ Adobe TechOps configure une tâche planifiée pour gérer automatiquement les données. Les données de flux Analytics sont transférées dans DWB pour traitement et transformation tous les soirs à partir de 21 h, heure de la suite de rapports.

・ Adobe TechOps traitera d’autres services gérés Adobe, notamment les sauvegardes de données, les comptes FTP, l’archivage des données et le transfert des données, le cas échéant.

・ Adobe TechOps configurera la grappe de production principale pour qu’elle contienne trois mois de données variables à réinitialiser et à retraiter chaque mois. Des mises à jour des recherches (Géographie, DeviceAtlas, Classifications standard) seront également effectuées dans le cadre de la tâche de retraitement. Par défaut, la tâche s’exécute le premier vendredi de chaque mois. Si nécessaire, le service à la clientèle peut modifier la planification.

Pour plus d’informations, contactez le service à la clientèle [Adobe](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
