---
description: Comment exporter, copier et mettre en signet depuis le plan de travail.
title: Utilisation du menu de vignette du plan de travail
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Utilisation du menu de vignette du plan de travail{#using-the-worktop-thumbnail-menu}

Comment exporter, copier et mettre en signet depuis le plan de travail.

Cliquez avec le bouton droit de la souris sur un espace de travail pour exporter, copier et marquer les fonctions du plan de travail.

![](assets/thumbnail_menu.png)

## Descriptions de l’interface {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Les éléments suivants sont disponibles dans le menu de miniature [!DNL Worktop] :

**Espace de travail du serveur :** *name*

S’affiche uniquement pour les espaces de travail du serveur non modifiés. Identifie l’espace de travail nommé comme l’espace de travail stocké sur le serveur.

**Date :** *jour et heure*

Date et heure de la dernière ouverture de l’espace de travail.

**Version locale de :** *name*

S’affiche uniquement pour les versions locales des espaces de travail du serveur. Identifie l’espace de travail nommé en tant que version locale modifiée d’un espace de travail stocké sur le serveur.

**Espace de travail de l’utilisateur :** *name*

S’affiche uniquement pour les espaces de travail utilisateur. Identifie l’espace de travail nommé comme un espace de travail qui existe uniquement sur l’ordinateur local.

**Calculer en arrière-plan**

S’affiche uniquement lorsque vous travaillez en ligne. Maintient les requêtes de l’espace de travail sélectionné en arrière-plan pendant que vous continuez à travailler. Lorsque cette option est sélectionnée, la miniature affiche les informations suivantes, qui indiquent la progression des requêtes :

* Utilisation : *n%* : indique que la requête est en cours de traitement et le pourcentage du traitement terminé.
* ** Chargement de requête nMB : taille totale du résultat de la requête. La charge de requête est proportionnelle à la charge de mémoire totale de votre serveur de Data Workbench, mais elle n’est pas directement corrélée. À titre indicatif, une charge de requête de 10 Mo ou plus peut peser sur votre système. La charge de requête répertoriée ne prend pas en compte la mise en grappe.

   >[!NOTE]
   >
   >Si l’option Calculer en arrière-plan reste sélectionnée, les requêtes de l’espace de travail sélectionné deviennent des requêtes permanentes, qui continuent à être mises à jour et utilisent la charge mémoire. Veillez à désélectionner l’option Calculer en arrière-plan lorsque vous avez terminé de travailler dans l’espace de travail.

**Exporter vers Excel**

Exportez les données de l’espace de travail dans un tableau de Microsoft Excel (fichiers .xls et .xslx). Lors de l’exportation d’un espace de travail vers Excel, Data Workbench exporte les données de certaines visualisations, légendes des dimensions et des valeurs, annotations de texte dans un nouveau classeur Excel avec une visualisation par feuille de calcul.

**Exporter vers un modèle Excel**

Exporter vers un modèle Excel (.xltx).

**Copier**

Copie l’espace de travail. Pour plus d’informations sur le collage d’un espace de travail copié, voir [Copie et collage des espaces de travail existants](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Restauration de la version du serveur**

S’affiche uniquement pour les versions locales des espaces de travail du serveur. Supprime la copie locale de cet espace de travail. L’original reste sur le serveur.

**Supprimer**

S’affiche uniquement pour les espaces de travail utilisateur. Supprime l’espace de travail de l’utilisateur, qui existe uniquement sur l’ordinateur local. Pour plus d’informations sur la suppression des espaces de travail du serveur de Data Workbench connecté, voir [Suppression de fichiers de votre profil de travail](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Enregistrer sur le serveur**

S’affiche uniquement pour les versions locales des espaces de travail du serveur et des utilisateurs et ne fonctionne que pour les utilisateurs disposant des autorisations appropriées. Enregistre la copie locale de l’espace de travail sur le serveur. Par défaut, les espaces de travail sont enregistrés dans le dossier `<profile name>\Workspaces\<tab name>` de travail approprié.

**Signet**

Mettez un espace de travail en signet pour récupérer rapidement plus tard.

Une icône de signet ![](assets/bookmark_icon.png) s’affiche au-dessus de l’espace de travail sur le plan de travail et le nom de l’espace de travail s’affiche dans le panneau Signet . ![](assets/bookmark_worktop.png)
