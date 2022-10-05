---
description: Mise à niveau des composants du serveur pour Data Workbench 6.2 et 6.2.2.
title: Mise à niveau du serveur DWB 6.1 vers 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# Mise à niveau du serveur DWB : 6.1 vers 6.2{#dwb-server-upgrade-to}

{{eol}}

Mise à niveau des composants du serveur pour Data Workbench 6.2 et 6.2.2.

## Problèmes de mise à niveau vers la version 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Le profil Attribution est configuré pour que les utilisateurs qui ont mis en oeuvre le profil SC d’Adobe utilisent le flux de données Analytics (SC/Insight). Par défaut, les événements Marketing et Conversion sont utilisés comme interactions par défaut évaluées dans les modèles basés sur des règles. Voir [Déploiement du profil d’attribution](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) pour plus d’informations.
* Pour les utilisateurs du profil SC Adobe effectuant une mise à niveau vers Data Workbench 6.2, si vous n’utilisez pas les configurations par défaut, vérifiez que la variable [!DNL x-bot_id] dans la variable [!DNL SC Fields.cfg] est correctement décodé et que la fonction [!DNL x-bot_id] est répertorié correctement dans la variable [!DNL Decoding Instructions.cfg] et le [!DNL Exclude Hit.cfg] fichiers . Ce problème se produira uniquement si vous avez modifié le fichier de configuration à partir de la configuration par défaut.
* Si vous avez supprimé des champs inutilisés dans la variable [!DNL Dataset > Log Processing > SC Fields.cfg] pour le profil SC d’Adobe, vous devez mettre à jour afin de prendre en compte les valeurs de champ mises à jour utilisées pour le profil d’attribution (voir [Déploiement du profil d’attribution](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Problèmes de mise à niveau vers la version 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Le **[!UICONTROL Browsers]** et **[!UICONTROL Operating Systems]** Les fichiers de recherche ne seront pas mis à jour dans l’ancien **[!UICONTROL Traffic]** profile (par exemple, [!DNL Lookups\Traffic\Browsers.txt)]. À la place, la configuration de la variable **[!UICONTROL Traffic]** profile utilisera le lot DeviceAtlas ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) pour fournir ces informations de configuration.
* La version 6.2.1 des Outils de données sera la dernière version à fournir un téléchargement de l’application cliente 32 bits. Tous les téléchargements d’application cliente ultérieurs seront en version 64 bits et continueront à exiger Windows 7 ou ultérieur. Les restrictions de mémoire de l’application 32 bits sont résolues avec l’introduction de l’application 64 bits à compter de la version 6.1.

>[!NOTE]
>
>La version 32 bits de l’application cliente Data Workbench peut rencontrer des problèmes potentiels liés aux limitations de mémoire lors de l’exécution de modèles prédictifs à l’aide des fonctionnalités de mise en grappe et de notation.
