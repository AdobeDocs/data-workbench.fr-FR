---
description: Vous trouverez ci-dessous les exigences et recommandations relatives à l’installation de Workstation (Client) en Data Workbench.
title: Exigences en matière de stations de travail
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Exigences en matière de stations de travail{#workstation-requirements}

Vous trouverez ci-dessous les exigences et recommandations relatives à l’installation de Workstation (Client) en Data Workbench.

Voir [Configuration requise du serveur](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/c-msr-server.html?lang=en) pour connaître la configuration requise supplémentaire du Data Workbench.

>[!IMPORTANT]
>
>Les composants serveur, serveur de rapports et client sont mis à niveau pour s’exécuter sur des systèmes d’exploitation Windows 64 bits.

**Avant de commencer**

Assurez-vous que les tâches suivantes sont terminées avant d’installer la station de travail du Data Workbench (client) :

* **** ***Ajout de*** processus exclus pour la protection des points d’entrée  *MS System Center sous les serveurs Windows 2012* pour les exécutables suivants :

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Cela permettra d’activer les droits de liste autorisée pour ces exécutables interfaces.

* **Installez Microsoft Excel pour exporter les données d’analyse.** Pour exporter des données des espaces de travail sous la forme de fichiers Microsoft Excel (  [!DNL .xls] ou  [!DNL .xlsx]), Excel doit être installé et enregistré sur l’ordinateur sur lequel vous installez Data Workbench. Si Excel n’a pas été enregistré et que Data Workbench tente d’y accéder pour la première fois, une boîte de dialogue d’enregistrement s’affiche. Si vous ne savez pas si la copie est enregistrée, démarrez Excel manuellement et si une boîte de dialogue d’enregistrement s’affiche, terminez le processus d’enregistrement.

   >[!NOTE]
   >
   >Avec la version 6.4 de Data Workbench, la prise en charge d’Excel 2007 a été abandonnée. En outre, comme Data Workbench ne s’exécute que sur l’architecture Microsoft Windows 64 bits, il est recommandé d’installer également une version 64 bits de Microsoft Excel.

* **Installation de l’Adobe  [!DNL Acrobat] pour l’impression des espaces de travail mis à l’échelle en PDF.** Pour imprimer des espaces de travail mis à l’échelle au format Adobe PDF, l’ordinateur sur lequel vous avez installé Data Workbench doit avoir  [!DNL Acrobat] installé Adobe.

* **Un accès à une imprimante pour les espaces de travail d’impression.** Pour imprimer des espaces de travail à partir de Data Workbench, l’ordinateur sur lequel vous installez Data Workbench doit avoir accès à une imprimante. Data Workbench peut imprimer des espaces de travail sur des imprimantes monochromes ou en couleur sans utiliser de postscript ni d’autres fonctions d’imprimante avancées. Pour des résultats optimaux, Adobe recommande d’imprimer les espaces de travail en couleur.
* **mettre en oeuvre des mesures de sécurité ;** Vous devez respecter les stratégies de sécurité d’entreprise standard de votre entreprise pour les ordinateurs Data Workbench. Pour servir ses Principaux objectifs, Data Workbench requiert uniquement la possibilité de se connecter à un serveur (via les ports 80 et 443) et à tout serveur collectant des données. Vous pouvez utiliser le matériel du Data Workbench à n’importe quelle autre fin tant que vous conservez le logiciel du Data Workbench et allouez au moins 10 Go d’espace de stockage à Data Workbench.
* Pour effectuer le rendu précis des visualisations, l’ordinateur sur lequel vous installez Workbench doit disposer d’un **adaptateur graphique** approprié (voir Exigences d’adaptateur graphique ci-dessous).

**Conditions requises du client Data Workbench**

**Système d’exploitation**

* Microsoft Windows 7 64 bits
* Microsoft Windows 8.1 64 bits
* Microsoft Windows 10 64 bits

>[!NOTE]
>
>Windows XP n’est pas pris en charge pour Data Workbench 6.1 et les versions ultérieures.

**Résolution**

* Obligatoire : 1 024 x 768 (XGA)
* Recommandé : 1 920 x 1 200 (WUXGA)

**Adaptateur graphique**

* Obligatoire : Accélération matérielle OpenGL pour la prise en charge d’OpenGL 3.2
* Recommandé : Adaptateur vidéo dédié (adaptateur NVIDIA ou ATI, par exemple)

**Processeur**

* Obligatoire : Intel ou AMD de 1,2 GHz ou plus
* Recommandé : ICore 2 Classe double

**RAM**

* Obligatoire : 2 Go
* Recommandé : 4 Go

**Connectivité**

* Obligatoire : Lien de 512 Kbit/s vers le DPU
* Recommandé : Lien de 2 Mbit/s ou plus rapide vers le DPU

**Système de fichiers**

NTFS

**Stockage de disque**

Au moins dix (10) Go ou plus d’espace disque disponible

**Impression**

Accès à l’imprimante (imprimantes couleur ou niveaux de gris) pour l’impression d’espaces de travail et de rapports

**Autre**

* Souris dédiée
* Environnement de travail à faible visibilité
* Surfaces de masque
