---
description: Data Workbench peut être configuré pour autoriser uniquement certains utilisateurs à modifier certains espaces de travail.
title: Configurer un espace de travail verrouillé
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configurer un espace de travail verrouillé{#configure-a-locked-workspace}

{{eol}}

Data Workbench peut être configuré pour autoriser uniquement certains utilisateurs à modifier certains espaces de travail.

Lorsqu’un espace de travail est verrouillé, les utilisateurs peuvent effectuer des sélections dans la plupart des visualisations et trier les données dans les tableaux, mais ils ne peuvent pas modifier l’espace de travail. Cette fonctionnalité empêche les utilisateurs d’apporter des modifications involontaires aux espaces de travail.

Les trois éléments suivants travaillent ensemble pour contrôler le verrouillage des espaces de travail :

* **Un dossier.lock ou *nom de l&#39;espace de travail*fichier .lock :** A [!DNL folder.lock] indique si les espaces de travail d’un dossier particulier sont verrouillés, alors qu’un espace de travail [!DNL name.lock] indique si un espace de travail particulier est verrouillé.

* **Le paramètre Déverrouiller dans le de [!DNL Insight.cfg] fichier :** Ce paramètre indique si l’utilisateur peut déverrouiller temporairement les espaces de travail.
* **L’option de menu Déverrouiller temporairement :** Lorsque le paramètre Déverrouiller dans le de l’utilisateur [!DNL Insight.cfg] est définie sur true, cette option apparaît automatiquement dans le menu de la barre de titre de chaque espace de travail verrouillé afin que l’utilisateur puisse la déverrouiller.

Pour plus d’informations sur [!DNL folder.lock] et espace de travail [!DNL name.lock] voir la section suivante. Pour plus d’informations sur la définition du paramètre Déverrouiller, voir [Définition du paramètre de déverrouillage](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Pour plus d’informations sur la variable [!DNL Temporarily Unlock menu] , voir [Déverrouillage d’un espace de travail](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
