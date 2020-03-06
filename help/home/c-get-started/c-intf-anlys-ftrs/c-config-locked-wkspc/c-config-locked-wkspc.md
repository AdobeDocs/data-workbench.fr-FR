---
description: Les outils de données peuvent être configurés pour permettre à certains utilisateurs seulement de modifier certains espaces de travail.
solution: Analytics
title: Configuration d’un espace de travail verrouillé
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration d’un espace de travail verrouillé{#configure-a-locked-workspace}

Les outils de données peuvent être configurés pour permettre à certains utilisateurs seulement de modifier certains espaces de travail.

Lorsqu’un espace de travail est verrouillé, les utilisateurs peuvent effectuer des sélections dans la plupart des visualisations et trier les données dans des tableaux, mais ils ne peuvent pas modifier l’espace de travail autrement. Cette fonctionnalité empêche les utilisateurs d’apporter des modifications non intentionnelles aux espaces de travail.

Les trois éléments ci-après permettent de contrôler ensemble le verrouillage des espaces de travail :

* **Fichier folder.lock ou nom **.lock de l’espace de travail :** Un [!DNL folder.lock] fichier indique si les espaces de travail d’un dossier particulier sont verrouillés, tandis qu’un [!DNL name.lock] fichier d’espace de travail indique si un espace de travail particulier est verrouillé.

* **Le paramètre Déverrouiller dans le[!DNL Insight.cfg]fichier d’un utilisateur :** Ce paramètre indique si l’utilisateur peut déverrouiller temporairement les espaces de travail verrouillés.
* **L’option de menu Déverrouiller temporairement :** Lorsque le paramètre Déverrouiller de l’utilisateur [!DNL Insight.cfg] est défini sur true, cette option s’affiche automatiquement dans le menu de la barre de titre de chaque espace de travail verrouillé pour permettre à l’utilisateur de le déverrouiller.

Pour plus d’informations sur [!DNL folder.lock] les fichiers [!DNL name.lock] de l’espace de travail, voir la section suivante. Pour plus d’informations sur la définition du paramètre Déverrouiller, voir [Définition du paramètre](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)Déverrouiller. Pour plus d’informations sur l’ [!DNL Temporarily Unlock menu] option, voir [Déverrouillage d’un espace de travail](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
