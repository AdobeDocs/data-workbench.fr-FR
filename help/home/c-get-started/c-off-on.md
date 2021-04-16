---
description: Informations relatives à l’utilisation du serveur de Data Workbench en ligne ou hors ligne.
title: Travail hors ligne et en ligne
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Travail hors ligne et en ligne{#working-offline-and-online}

Informations relatives à l’utilisation du serveur de Data Workbench en ligne ou hors ligne.

Le Data Workbench télécharge automatiquement les mises à jour du profil et de ses données à partir du serveur Data Workbench si vous disposez d’une connexion réseau à [!DNL server] et que vous travaillez en ligne. Si vous n’avez pas spécifié de travailler en ligne, le Data Workbench charge le profil et ses données depuis le cache de votre ordinateur. Dans ce cas, vous visualisez la version du profil et ses données téléchargées la dernière fois que vous avez travaillé en ligne avec le profil.

Le travail hors ligne des offres offre un avantage de vitesse de traitement car vous travaillez à partir du cache local et que vous interrogez les données sur votre propre ordinateur. Lorsque vous travaillez en ligne, chaque requête doit revenir au serveur Data Workbench, ce qui prend plus de temps et vous force à rivaliser avec d&#39;autres utilisateurs en ligne pour les ressources du serveur. Tant que vous disposez d’une connexion réseau au serveur Data Workbench, le fait de travailler hors connexion empêche le serveur Data Workbench de mettre à jour les profils ou les données de votre Data Workbench, mais cela ne vous empêche pas d’enregistrer des éléments sur le serveur Data Workbench.

En raison de la possibilité de travailler hors connexion, le serveur Data Workbench est dimensionné pour gérer une certaine quantité d&#39;entrées de trafic en temps réel et une certaine quantité de données dans le jeu de données, ainsi qu&#39;un certain nombre d&#39;utilisateurs Data Workbench, mais il n&#39;est pas nécessaire de le dimensionner pour prendre en charge le nombre maximal d&#39;utilisateurs simultanés (ce qui n&#39;arrive pas souvent en pratique). Comme les utilisateurs recherchent généralement les tendances et les ratios, ils explorent les données au fur et à mesure, et dans la plupart des cas, il n’est pas nécessaire d’avoir des comptes exacts. S&#39;il est nécessaire d&#39;effectuer des requêtes et de résoudre des comptes exacts à l&#39;aide des données actuelles, vous pouvez travailler en ligne et obtenir cela, mais les requêtes prennent plus de temps à résoudre à 100 %.

**Pour travailler en ligne ou hors ligne**

Dans la barre latérale, cliquez sur le paramètre **[!UICONTROL Connection]** et cliquez sur **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Lorsque vous travaillez en ligne, le Data Workbench se connecte au serveur Data Workbench et synchronise les informations de votre ordinateur avec le profil et ses informations de jeu de données résidant sur le serveur Data Workbench.

La configuration par défaut du Data Workbench consiste à travailler hors connexion, mais comme décrit dans la section suivante, chaque utilisateur peut modifier son fichier [!DNL Insight.cfg] pour que son instance de Data Workbench fonctionne en ligne par défaut.

**Pour travailler en ligne par défaut**

1. Accédez au répertoire d’installation d’Insight.
1. Ouvrez le fichier [!DNL Insight.cfg] dans un éditeur de texte.
1. Ajoutez la ligne mise en surbrillance dans le fichier comme indiqué dans l&#39;exemple suivant :

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La prochaine fois que vous ouvrirez le Data Workbench, il se connectera au serveur du Data Workbench et fonctionnera en ligne par défaut.
