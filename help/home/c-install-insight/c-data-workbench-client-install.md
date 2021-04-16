---
description: Vous trouverez ci-dessous la configuration requise et les recommandations pour installer le poste de travail (client) en Data Workbench.
title: Exigences en matière de stations de travail
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Exigences en matière de stations de travail{#workstation-requirements}

Vous trouverez ci-dessous la configuration requise et les recommandations pour installer le poste de travail (client) en Data Workbench.

Voir [Configuration requise pour le serveur](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) pour connaître la configuration requise pour les Data Workbench supplémentaires.

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

**Avant de commencer**

Assurez-vous que les tâches suivantes sont terminées avant d’installer la station de travail Data Workbench (client) :

* **** ***AddExcluded*** Process for  *MS System Center Endpoint Protection in Windows 2012* Serversers pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Cela permettra d&#39;activer les droits de liste autorisée pour ces exécutables d&#39;interface.

* **Installez Microsoft Excel pour exporter les données d&#39;analyse.** Pour exporter les données des espaces de travail sous forme de fichiers Microsoft Excel (  [!DNL .xls] ou  [!DNL .xlsx]), Excel doit être installé et enregistré sur l&#39;ordinateur sur lequel vous installez le Data Workbench. Si Excel n&#39;a pas été enregistré et que le Data Workbench tente d&#39;y accéder pour la première fois, une boîte de dialogue d&#39;enregistrement s&#39;affiche. Si vous ne savez pas si la copie est enregistrée, début Excel manuellement et si une boîte de dialogue d&#39;enregistrement s&#39;affiche, effectuez le processus d&#39;enregistrement.

   >[!NOTE]
   >
   >Avec la publication du Data Workbench 6.4, la prise en charge d&#39;Excel 2007 a été interrompue. En outre, comme le Data Workbench ne s’exécute que sur Microsoft Windows pour l’architecture 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Installation de l’Adobe  [!DNL Acrobat] pour l’impression d’espaces de travail mis à l’échelle au format PDF.** Pour imprimer les espaces de travail mis à l’échelle au format Adobe PDF, l’ordinateur sur lequel vous avez installé le Data Workbench doit avoir un Adobe  [!DNL Acrobat] installé.

* **Accès à une imprimante pour l’impression d’espaces de travail.** Pour imprimer des espaces de travail à partir d’un Data Workbench, l’ordinateur sur lequel vous installez le Data Workbench doit avoir accès à une imprimante. Le Data Workbench peut imprimer des espaces de travail sur des imprimantes monochromes ou en couleur et ne nécessite pas de post-script ou d’autres fonctions avancées d’imprimante. Pour des résultats optimaux, l’Adobe recommande l’impression d’espaces de travail en couleur.
* **Mettre en oeuvre des mesures de sécurité.** Suivez les règles de sécurité d&#39;entreprise habituelles de votre société pour les ordinateurs Data Workbench. Pour atteindre ses objectifs Principaux, le Data Workbench ne nécessite que la possibilité de se connecter à un serveur (via les ports 80 et 443) et à tout serveur collectant des données. Vous pouvez utiliser le matériel du Data Workbench pour tout autre usage tant que vous maintenez le logiciel du Data Workbench et allouez au moins 10 Go d’espace d’enregistrement au Data Workbench.
* Pour effectuer le rendu précis des visualisations, l&#39;ordinateur sur lequel vous installez le pupitre doit disposer d&#39;une **carte graphique** appropriée (voir Configuration requise pour les cartes graphiques ci-dessous).

**Conditions requises du client Data Workbench**

**Système d’exploitation**

* Microsoft Windows 7 64 bits
* Microsoft Windows 8.1 64 bits
* Microsoft Windows 10 64 bits

>[!NOTE]
>
>Windows XP n&#39;est pas pris en charge pour les versions 6.1 et ultérieures du Data Workbench.

**Résolution**

* Obligatoire : 1 024 x 768 (XGA)
* Recommandé : 1 920 x 1 200 (WUXGA)

**Carte graphique**

* Obligatoire : Accélération matérielle OpenGL pour la prise en charge d&#39;OpenGL 3.2
* Recommandé : Carte vidéo dédiée (par exemple, carte NVIDIA ou ATI)

**Processeur**

* Obligatoire : Intel ou AMD de 1,2 GHz ou plus
* Recommandé : Classe double ICore 2

**RAM**

* Obligatoire : 2 Go
* Recommandé : 4 Go

**Connectivité**

* Obligatoire : Lien de 512 Kbits/s vers l’unité de traitement
* Recommandé : Lien de 2 Mbit/s ou plus rapide vers le processeur de stockage

**Système de fichiers**

NTFS

**Enregistrement de disque**

Au moins dix (10) Go d&#39;espace disque disponible ou plus

**Impression**

Accès à l’imprimante (imprimantes en couleur ou en niveaux de gris) pour l’impression des espaces de travail et des rapports

**Autre**

* Souris dédiée
* Environnement de travail à faible luminosité
* Moniteur à surface matée
