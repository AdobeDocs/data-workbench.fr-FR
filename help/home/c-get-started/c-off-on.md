---
description: Informations sur l’utilisation du serveur de Data Workbench en ligne ou hors ligne.
title: Travail hors ligne et en ligne
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Travail hors ligne et en ligne{#working-offline-and-online}

{{eol}}

Informations sur l’utilisation du serveur de Data Workbench en ligne ou hors ligne.

Data Workbench télécharge automatiquement les mises à jour du profil et de ses données à partir du serveur du Data Workbench si vous êtes connecté au réseau [!DNL server] et travaillent en ligne. Si vous n’avez pas spécifié de fonctionner en ligne, Data Workbench charge le profil et ses données à partir du cache de votre ordinateur. Dans ce cas, vous affichez la version du profil et ses données qui ont été téléchargées la dernière fois que vous avez travaillé en ligne avec le profil.

Le travail hors ligne offre un avantage de vitesse de traitement, car vous travaillez à partir du cache local et interrogez les données sur votre propre ordinateur. Lorsque vous travaillez en ligne, chaque requête doit revenir au serveur du Data Workbench, ce qui prend plus de temps et vous force à rivaliser avec d&#39;autres utilisateurs en ligne pour les ressources du serveur. Tant que vous disposez d’une connexion réseau au serveur de Data Workbench, travailler hors ligne empêche le serveur de Data Workbench de mettre à jour les profils ou les données de votre Data Workbench, mais cela ne vous empêche pas d’enregistrer les éléments sur le serveur de Data Workbench.

En raison de la possibilité de travailler hors ligne, le serveur de Data Workbench est dimensionné pour gérer une certaine quantité d’entrée de trafic en temps réel et une certaine quantité de données dans le jeu de données, ainsi qu’un certain nombre d’utilisateurs Data Workbench, mais il n’est pas nécessaire de le dimensionner pour prendre en charge le nombre maximal d’utilisateurs simultanés (ce qui n’est en pratique pas souvent le cas). Comme les utilisateurs recherchent généralement les tendances et les ratios, en explorant les données au fur et à mesure, dans la plupart des cas, vous n’avez pas besoin de chiffres exacts. S’il est nécessaire d’effectuer des requêtes et de résoudre les problèmes avec les données actuelles, vous pouvez travailler en ligne et obtenir ce résultat, mais la résolution des requêtes prend plus de temps pour atteindre 100 %.

**Pour travailler en ligne ou hors ligne**

Dans la barre latérale, cliquez sur le **[!UICONTROL Connection]** et cliquez sur **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Lorsque vous travaillez en ligne, Data Workbench se connecte au serveur du Data Workbench et synchronise les informations de votre ordinateur avec le profil et ses informations de jeu de données résidant sur le serveur du Data Workbench.

La configuration par défaut de Data Workbench consiste à travailler hors ligne, mais comme décrit dans la section suivante, chaque utilisateur peut modifier sa [!DNL Insight.cfg] pour que leur instance de Data Workbench fonctionne en ligne par défaut.

**Pour travailler en ligne par défaut**

1. Accédez au répertoire d’installation d’Insight.
1. Ouvrez le [!DNL Insight.cfg] dans un éditeur de texte.
1. Ajoutez la ligne surlignée au fichier, comme illustré dans l’exemple suivant :

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La prochaine fois que vous ouvrez Data Workbench, il se connecte au serveur du Data Workbench et fonctionne en ligne par défaut.
