---
description: Le Data Workbench peut être configuré pour permettre à certains utilisateurs seulement de modifier certains espaces de travail.
title: Configurer un espace de travail verrouillé
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configuration d’un espace de travail verrouillé{#configure-a-locked-workspace}

Le Data Workbench peut être configuré pour permettre à certains utilisateurs seulement de modifier certains espaces de travail.

Bien qu’un espace de travail soit verrouillé, les utilisateurs peuvent effectuer des sélections dans la plupart des visualisations et trier les données dans des tableaux, mais ils ne peuvent pas changer l’espace de travail autrement. Cette fonctionnalité empêche les utilisateurs d’apporter des modifications involontaires aux espaces de travail.

Les trois éléments suivants fonctionnent ensemble pour contrôler le verrouillage des espaces de travail :

* **Un fichier folder.lock ou  *workspace name*.lock :** Un  [!DNL folder.lock] fichier spécifie si les espaces de travail d’un dossier particulier sont verrouillés, tandis qu’un  [!DNL name.lock] fichier workspace indique si un espace de travail particulier est verrouillé.

* **Le paramètre Déverrouiller dans le  [!DNL Insight.cfg] fichier d’un utilisateur :** Ce paramètre indique si cet utilisateur peut déverrouiller temporairement des espaces de travail verrouillés.
* **Option de menu Déverrouiller temporairement :** lorsque le paramètre Déverrouiller de l’utilisateur  [!DNL Insight.cfg] est défini sur true, cette option s’affiche automatiquement dans le menu de la barre de titre de chaque espace de travail verrouillé pour permettre à l’utilisateur de le déverrouiller.

Pour plus d&#39;informations sur les fichiers [!DNL folder.lock] et l&#39;espace de travail [!DNL name.lock], consultez la section suivante. Pour plus d’informations sur la définition du paramètre Déverrouiller, voir [Définition du paramètre Déverrouiller](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Pour plus d’informations sur l’option [!DNL Temporarily Unlock menu], voir [Déverrouillage d’un espace de travail](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
