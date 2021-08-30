---
description: Pour lancer le processus d’intégration d’Adobe Data Workbench (DWB), un composant de Adobe Analytics Premium (AAP), procédez comme suit.
title: Instructions d’intégration de base pour DWB Managed Services
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Instructions d’intégration de base pour DWB Managed Services{#basic-onboarding-instructions-for-dwb-managed-services}

Pour lancer le processus d’intégration d’Adobe Data Workbench (DWB), un composant de Adobe Analytics Premium (AAP), procédez comme suit.

Ces instructions d’intégration concernent les clients qui implémentent un Data Workbench avec une seule suite de rapports à l’aide de services gérés par Adobe sans services de conseil. Si vous êtes un nouveau client AAP qui implémente DWB, l’équipe d’intégration d’Adobe sera votre premier contact. Si vous effectuez une mise à niveau à partir d’Adobe Analytics standard ou d’une version antérieure de DWB, un gestionnaire de succès client Adobe vous aidera.

## Infos sur l’intégration : Ce dont nous avons besoin de vous {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe vous contactera pour :

* Identifiez un utilisateur Principal pour DWB afin de générer un certificat spécifique à cet utilisateur sur le répertoire réseau. L’utilisateur Principal agira également comme personne de référence pour interagir avec l’assistance clientèle d’Adobe.
* Identifiez la suite de rapports à charger dans DWB.

Les équipes Digital Marketing Adobe récupéreront ensuite vos informations pour créer des profils, définir des comptes et fournir un fichier de configuration pour DWB.

**Tâches d’intégration des Adobes**

* L’assistance clientèle d’Adobe crée un compte sous licence DWB. L’assistance clientèle d’Adobe génère un certificat DWB pour l’utilisateur Principal.
* Le service à la clientèle d’Adobe définit l’utilisateur Principal comme un &quot;utilisateur pris en charge&quot;, la personne identifiée pour les appels pris en charge et la résolution de problème.
* L’Assistance clientèle d’Adobe charge le package logiciel sur le portail de licences et de logiciels DWB (profil SoftDocs/Software et Docs) à télécharger dans votre entreprise.
* L’équipe des opérations techniques d’Adobe prépare les environnements de production et de développement et leurs profils (par contrat) pour la DWB.
* L’équipe des opérations techniques d’Adobe configure les flux de données et les scripts de gestion des profils.
* L’équipe TechOps d’Adobe crée et envoie le fichier de configuration DWB (Insight.cfg) à l’équipe d’intégration d’Adobe responsable des tâches d’intégration associées à votre organisation.

Après avoir personnalisé vos flux de données et généré des informations d’identification, des certificats et une configuration de profil, l’Assistance clientèle d’Adobe enverra votre fichier de configuration et vos informations d’identification pour passer à l’étape suivante.

## Accès à vos fichiers d’installation personnalisés {#section-26962bf57fef435dbd1c5486d4b6f688}

Vous recevrez ces fichiers de configuration de l’Assistance clientèle d’Adobe pour installer la station de travail DWB sur votre ordinateur client.

* Votre fichier de configuration DWB personnalisé (Insight.cfg)

   Ce fichier de configuration sur l’ordinateur client comprend des connexions à vos serveurs DWB gérés.

* Connectez-vous au portail de licences pour télécharger l’assistant de configuration DWB et le certificat requis (fichier .pem) avec le nom de votre Principal utilisateur.

**Téléchargement de fichiers de configuration supplémentaires**

1. Accédez à : license.visualsciences.com pour télécharger votre certificat de licence et le fichier exécutable de l’assistant de configuration DWB.
1. Saisissez votre organisation (nom du compte), le nom de l’utilisateur Principal et le mot de passe que vous avez reçu de l’assistance clientèle d’Adobe, puis cliquez sur Connexion.

   >[!NOTE]
   >
   >À ce stade, votre navigateur peut vous inviter à présenter un certificat numérique. Si tel est le cas, cliquez sur Annuler pour fermer la boîte de dialogue.

1. Recherchez le certificat émis pour votre instance d’Adobe Data Workbench (`<PrimaryUser>`.pem) dans la section Téléchargements et téléchargez-le.
1. Recherchez Standard Client Installer dans la section Téléchargements pour télécharger l’assistant de configuration DWB (fichier InsightSetup-x.xx.exe).
1. Après avoir reçu et téléchargé les fichiers de l’assistance clientèle d’Adobe, exécutez l’assistant de configuration DWB pour installer le logiciel de poste de travail sur votre ordinateur client.

>[!NOTE]
L’assistant de configuration DWB vous guide tout au long de l’installation du poste de travail client DWB et vous aide à localiser les fichiers Insight.cfg et `<PrimaryUser>`.pem à placer dans les dossiers requis. Le fichier Insight.cfg réside dans le fichier Insight.exe du poste de travail client installé. Le fichier `<PrimaryUser>`.pem se trouve dans le dossier Certificats avec le fichier trust_ca_cert.pem . Tous les fichiers de certificat et de configuration doivent être présents pour que DWB fonctionne.

Pour plus d’informations, voir [Assistant de configuration DWB](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html).

## Connexion à vos serveurs DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Vos serveurs gérés sont identifiés dans le fichier Insight.cfg que vous recevez de l’assistance clientèle d’Adobe et que vous résidez sur votre poste de travail client. Les opérations techniques d’Adobe configureront vos serveurs et l’assistance clientèle d’Adobe ajoutera des références à ces serveurs et profils gérés dans le fichier Insight.cfg avant de vous l’envoyer. (La configuration des connexions au serveur à l’étape 12 de la documentation de l’assistant de configuration DWB est terminée.)

>[!NOTE]
Dans l’espace de travail Configuration de la station de travail sur la station de travail cliente DWB, vous pourrez voir vos serveurs et profils connectés.

**Adobe Managed Services**

・ Les opérations techniques d’Adobe gèrent l’infrastructure, notamment le réseau, le centre de données, les serveurs et le stockage. La surveillance de l’infrastructure et la réponse aux alertes surviennent 24h/24, 7j/7 pour les alertes nécessitant une action TechOps. Pour d’autres alertes, les opérations techniques avertissent l’assistance clientèle d’Adobe de les coordonner avec vous.

・ Les opérations techniques d’Adobe effectuent les mises à jour de maintenance et de micrologiciel pour vos serveurs gérés. Pour les périodes de maintenance provoquant des temps d’arrêt, vous recevrez au moins deux semaines à l’avance des notifications de la fenêtre de maintenance de l’assistance clientèle. Les opérations techniques d’Adobe répondront aux besoins immédiats le plus rapidement possible. Les notifications dépendent de l’urgence et seront résolues une fois le planning connu.

・ Les opérations techniques d’Adobe configurent une tâche planifiée pour gérer automatiquement les données. Les données de flux Analytics sont déplacées dans la base de données pour traitement et transformation tous les soirs à partir de 21h00, heure de la suite de rapports.

・ Les opérations techniques d’Adobe traiteront d’autres services gérés Adobe, notamment les sauvegardes de données, les comptes FTP, l’archivage des données et le transfert de données, le cas échéant.

・ Les opérations techniques d’Adobe configureront la grappe de production Principale de sorte qu’elle contienne trois mois de données flottantes qui seront réinitialisées et traitées chaque mois. Des mises à jour des recherches (Geography, DeviceAtlas, Standard Classifications) seront également effectuées dans le cadre de la tâche de retraitement. Par défaut, la tâche s’exécute le premier vendredi de chaque mois. Si nécessaire, le planning peut être modifié par l’assistance clientèle.

Pour plus d’informations, contactez [l’ Assistance clientèle Adobe](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
