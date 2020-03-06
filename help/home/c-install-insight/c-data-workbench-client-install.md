---
description: Vous trouverez ci-dessous la configuration requise et des recommandations pour l’installation de Workstation (Client) dans les Outils de données.
solution: Analytics
title: Configuration requise pour les stations de travail
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Configuration requise pour les stations de travail{#workstation-requirements}

Vous trouverez ci-dessous la configuration requise et des recommandations pour l’installation de Workstation (Client) dans les Outils de données.

Voir Configuration requise [pour](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) le serveur pour connaître la configuration requise pour les Outils de données.

>[!IMPORTANT]
>
>Le serveur, le serveur de rapports et les composants client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

**Avant de commencer**

Assurez-vous que les tâches suivantes sont terminées avant d’installer la station de travail des outils de données (client) :

* **Ajoutez** des processus ****** exclus pour la protection des points de fin System Center ** MS sur les serveurs Windows 2012 pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Cela permettra d&#39;accorder des droits de &quot;liste blanche&quot; pour ces exécutables interfacés.

* **Installez Microsoft Excel pour exporter les données d&#39;analyse.** Pour exporter les données des espaces de travail sous forme de fichiers Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), Excel doit être installé et enregistré sur l’ordinateur sur lequel vous installez les outils de données. Si Excel n’a pas été enregistré et que les Outils de données tentent d’y accéder pour la première fois, Excel affiche une boîte de dialogue d’enregistrement. Si vous ne savez pas si la copie est enregistrée, lancez Excel manuellement et si une boîte de dialogue d’enregistrement s’affiche, terminez le processus d’enregistrement.

   >[!NOTE]
   >
   >Avec la version 6.4 des Outils de données, la prise en charge d’Excel 2007 a été interrompue. En outre, étant donné que les outils de données s’exécutent uniquement sur Microsoft Windows pour une architecture 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Installation d’Adobe[!DNL Acrobat]pour l’impression d’espaces de travail mis à l’échelle au format PDF.** Pour imprimer des espaces de travail mis à l’échelle au format Adobe PDF, Adobe doit être installé sur l’ordinateur sur lequel vous avez installé les Outils de données. [!DNL Acrobat]

* **Accès à une imprimante pour l’impression des espaces de travail.** Pour imprimer des espaces de travail à partir des Outils de données, l’ordinateur sur lequel vous installez les Outils de données doit avoir accès à une imprimante. Les outils de données peuvent imprimer des espaces de travail sur des imprimantes monochromes ou en couleur et ne nécessitent pas de fonctions d’imprimante avancées ou PostScript. Pour des résultats optimaux, Adobe recommande d’imprimer les espaces de travail en couleur.
* **Mettre en oeuvre des mesures de sécurité.** Suivez les règles de sécurité d’entreprise habituelles de votre entreprise pour les ordinateurs Outils de données. Pour servir ses objectifs principaux, les outils de données doivent uniquement pouvoir se connecter à un serveur (via les ports 80 et 443) et à tout serveur collectant des données. Vous pouvez utiliser le matériel des outils de données pour toute autre fin tant que vous conservez le logiciel des outils de données et allouez au moins 10 Go d’espace de stockage aux outils de données.
* Pour effectuer le rendu précis des visualisations, l’ordinateur sur lequel vous installez les outils doit disposer d’une carte **graphique** appropriée (voir Configuration requise pour les cartes graphiques ci-dessous).

**Exigences du client des outils de données**

**Système d’exploitation**

* Microsoft Windows 7 64 bits
* Microsoft Windows 8.1 64 bits
* Microsoft Windows 10 64 bits

>[!NOTE]
>
>Windows XP n’est pas pris en charge pour les outils de données version 6.1 et ultérieure.

**Résolution**

* Obligatoire : 1 024 x 768 (XGA)
* Recommandé : 1 920 x 1 200 (WUXGA)

**Carte graphique**

* Obligatoire : Accélération matérielle OpenGL pour la prise en charge d’OpenGL 3.2
* Recommandé : Adaptateur vidéo dédié (adaptateur NVIDIA ou ATI, par exemple)

**Processeur**

* Obligatoire : 1,2 GHz ou plus Intel ou AMD
* Recommandé : Classe ICore 2 Duo

**RAM**

* Obligatoire : 2 Go
* Recommandé : 4 Go

**Connectivité**

* Obligatoire : Lien 512 Kbit/s vers le DPU
* Recommandé : Lien de 2 Mbit/s ou plus rapide vers le DPU

**Système de fichiers**

NTFS

**Stockage sur disque**

Au moins dix (10) Go d’espace disque disponible ou plus

**Impression**

Accès à l’imprimante (imprimantes couleur ou en niveaux de gris) pour les espaces de travail d’impression et les rapports

**Autre**

* Souris dédiée
* Environnement de travail à faible luminosité
* Moniteur à surface mat

