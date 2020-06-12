---
description: Vous trouverez ci-dessous les conditions requises et les recommandations relatives à l’installation de la station de travail (client) dans les Outils de données.
solution: Analytics
title: Exigences relatives aux stations de travail
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---


# Exigences relatives aux stations de travail{#workstation-requirements}

Vous trouverez ci-dessous les conditions requises et les recommandations relatives à l’installation de la station de travail (client) dans les Outils de données.

Voir Configuration requise [pour](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) le serveur pour connaître la configuration requise pour les Outils de données.

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

**Avant de commencer**

Assurez-vous que les tâches suivantes sont terminées avant d’installer la station de travail des outils de données (client) :

* **Ajouter** les processus ****** exclus pour la protection des points de terminaison *MS System Center sur les serveurs* Windows 2012 pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Cela permettra d&#39;autoriser les droits pour ces exécutables interfacés.

* **Installez Microsoft Excel pour exporter les données d&#39;analyse.** Pour exporter les données des espaces de travail sous forme de fichiers Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), Excel doit être installé et enregistré sur l’ordinateur sur lequel vous installez les outils de données. Si Excel n’a pas été enregistré et que les Outils de données tentent d’y accéder pour la première fois, Excel affiche une boîte de dialogue d’enregistrement. Si vous ne savez pas si la copie est enregistrée, début Excel manuellement et si une boîte de dialogue d&#39;enregistrement s&#39;affiche, effectuez le processus d&#39;enregistrement.

   >[!NOTE]
   >
   >Avec la version 6.4 des Outils de données, la prise en charge d’Excel 2007 a été interrompue. En outre, étant donné que les outils de données s’exécutent uniquement sur Microsoft Windows pour une architecture 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Installation de Adobe[!DNL Acrobat]pour l’impression d’espaces de travail mis à l’échelle au format PDF.** Pour imprimer des espaces de travail mis à l’échelle au format PDF Adobe, Adobe doit être [!DNL Acrobat] installé sur l’ordinateur sur lequel vous avez installé les Outils de données.

* **Accès à une imprimante pour l’impression d’espaces de travail.** Pour imprimer des espaces de travail à partir des Outils de données, l’ordinateur sur lequel vous installez les Outils de données doit avoir accès à une imprimante. Les outils de données peuvent imprimer des espaces de travail sur des imprimantes monochromes ou en couleur et ne nécessitent pas de post-script ou d’autres fonctions d’imprimante avancées. Pour des résultats optimaux, Adobe recommande l’impression d’espaces de travail en couleur.
* **Mettre en oeuvre des mesures de sécurité.** Suivez les règles de sécurité d’entreprise habituelles de votre société pour les ordinateurs Outils de données. Pour servir ses objectifs principaux, les outils de données ne nécessitent que la possibilité de se connecter à un serveur (via les ports 80 et 443) et à tout serveur collectant des données. Vous pouvez utiliser le matériel des outils de données à toute autre fin tant que vous conservez le logiciel des outils de données et que vous allouez au moins 10 Go d’espace d’enregistrement aux outils de données.
* Pour effectuer le rendu précis des visualisations, un adaptateur **** graphique approprié doit être installé sur l’ordinateur sur lequel vous installez le pupitre (voir la section Configuration requise pour les cartes graphiques ci-dessous).

**Exigences du client des outils de données**

**Système d’exploitation**

* Microsoft Windows 7 64 bits
* Microsoft Windows 8.1 64 bits
* Microsoft Windows 10 64 bits

>[!NOTE]
>
>Windows XP n&#39;est pas pris en charge pour les outils de données version 6.1 et ultérieure.

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
* environnement de travail à faible luminosité
* Moniteur à surface matée

