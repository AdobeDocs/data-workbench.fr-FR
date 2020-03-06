---
description: Informations sur l’utilisation du serveur Outils de données en ligne ou hors ligne.
solution: Analytics
title: Travail hors ligne et en ligne
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Travail hors ligne et en ligne{#working-offline-and-online}

Informations sur l’utilisation du serveur Outils de données en ligne ou hors ligne.

Les outils de données téléchargent automatiquement les mises à jour du profil et de ses données à partir du serveur des outils de données si vous disposez d’une connexion réseau au [!DNL server] et que vous travaillez en ligne. Si vous n’avez pas spécifié de travailler en ligne, les outils de données chargent le profil et ses données à partir du cache de votre ordinateur. Dans ce cas, vous affichez la version du profil et ses données qui ont été téléchargées la dernière fois que vous avez travaillé en ligne avec le profil.

Le travail hors connexion offre un avantage de vitesse de traitement car vous travaillez à partir du cache local et interrogez les données sur votre propre ordinateur. Lorsque vous travaillez en ligne, chaque requête doit revenir au serveur Outils de données, ce qui prend plus de temps et vous force à rivaliser avec d’autres utilisateurs en ligne pour les ressources du serveur. Tant que vous disposez d’une connexion réseau au serveur Outils de données, le fait de travailler hors connexion empêche le serveur Outils de données de mettre à jour les profils ou les données de vos Outils de données, mais cela ne vous empêche pas d’enregistrer les éléments sur le serveur Outils de données.

En raison de la possibilité de travailler hors connexion, le serveur Outils de données est dimensionné pour gérer une certaine quantité d’entrées de trafic en temps réel et une certaine quantité de données dans le jeu de données, ainsi que certains utilisateurs des Outils de données. Toutefois, il n’est pas nécessaire de le dimensionner pour prendre en charge le nombre maximal d’utilisateurs simultanés (ce qui n’est pas le cas dans la pratique). Comme les utilisateurs recherchent généralement les tendances et les ratios, ils explorent les données au fur et à mesure, dans la plupart des cas, il n’est pas nécessaire de connaître les valeurs exactes. S&#39;il est nécessaire d&#39;interroger et de résoudre les comptes exacts à l&#39;aide des données actuelles, vous pouvez travailler en ligne et obtenir cela, mais les requêtes prennent plus de temps à résoudre jusqu&#39;à 100 %.

**Pour travailler en ligne ou hors ligne**

Dans la barre latérale, cliquez sur le **[!UICONTROL Connection]** paramètre et cliquez sur **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Lorsque vous travaillez en ligne, les outils de données se connectent au serveur des outils de données et synchronisent les informations de votre ordinateur avec le profil et ses informations de jeu de données résidant sur le serveur des outils de données.

La configuration par défaut des Outils de données fonctionne hors connexion, mais comme décrit dans la section suivante, chaque utilisateur peut modifier son [!DNL Insight.cfg] fichier pour que son instance fonctionne en ligne par défaut.

**Pour travailler en ligne par défaut**

1. Accédez au répertoire d’installation d’Insight.
1. Ouvrez le [!DNL Insight.cfg] fichier dans un éditeur de texte.
1. Ajoutez la ligne mise en surbrillance au fichier comme illustré dans l’exemple suivant :

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La prochaine fois que vous ouvrirez Outils de données, il se connectera au serveur Outils de données et fonctionnera en ligne par défaut.
