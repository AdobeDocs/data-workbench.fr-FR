---
description: Mise à niveau des composants de serveur pour les outils de données 6.2 et 6.2.2.
title: DWB Server version 6.1 à 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Mise à niveau du serveur DWB : 6.1 à 6.2{#dwb-server-upgrade-to}

Mise à niveau des composants de serveur pour les outils de données 6.2 et 6.2.2.

## Problèmes de mise à niveau vers la version 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Le profil d’attribution est configuré pour que les utilisateurs qui ont mis en oeuvre le profil Adobe SC utilisent le flux de données Analytics (SC/Insight). Par défaut, les événements Marketing et Conversion sont utilisés comme interactions par défaut évaluées dans les modèles basés sur des règles. Voir [Déploiement du profil](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html) d’attribution pour plus d’informations.
* Pour les utilisateurs de la mise à niveau du profil Adobe SC vers Data Workbench 6.2, si vous n’utilisez pas les configurations par défaut, vérifiez que la [!DNL x-bot_id] valeur du [!DNL SC Fields.cfg] fichier est décodée correctement et que le [!DNL x-bot_id] champ est correctement répertorié dans les fichiers [!DNL Decoding Instructions.cfg] et [!DNL Exclude Hit.cfg] . Ce problème se produira uniquement si vous avez modifié le fichier de configuration à partir de la configuration par défaut.
* Si vous avez supprimé des champs inutilisés dans le [!DNL Dataset > Log Processing > SC Fields.cfg] fichier pour le profil Adobe SC, vous devrez effectuer une mise à jour afin de tenir compte des valeurs de champ mises à jour utilisées pour le profil d’attribution (voir [Déploiement du profil](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)d’attribution).

## Problèmes de mise à niveau vers la version 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Les fichiers **[!UICONTROL Browsers]** et **[!UICONTROL Operating Systems]** de recherche ne seront pas mis à jour dans le profil hérité **[!UICONTROL Traffic]** (par exemple, [!DNL Lookups\Traffic\Browsers.txt)]). Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* La version 6.2.1 des Outils de données sera la dernière version à fournir un téléchargement de l’application cliente 32 bits. Tous les téléchargements d’application cliente ultérieurs seront en version 64 bits et continueront à exiger Windows 7 ou ultérieur. Les restrictions de mémoire de l’application 32 bits sont résolues avec l’introduction de l’application 64 bits à compter de la version 6.1.

>[!NOTE]
>
>La version 32 bits de l’application cliente Outils de données peut rencontrer des problèmes potentiels liés aux limitations de mémoire lors de l’exécution de modèles prédictifs à l’aide des fonctions de mise en grappe et de notation.

