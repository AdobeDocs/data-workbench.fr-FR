---
description: Adobe Data Workbench fournit des outils et des processus pour préparer vos données à se conformer au Règlement général sur la protection des données (RGPD).
title: Prise en charge de Data Workbench pour le RGPD
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# Prise en charge de Data Workbench pour le RGPD

{{eol}}

Adobe Data Workbench fournit des outils et des processus pour préparer vos données à la conformité aux [!DNL General Data Protection Regulations] (RGPD).

Comme toutes les solutions Adobe Analytics, Data Workbench prend en charge le RGPD en fournissant le nettoyage, la suppression et l’étiquetage des variables analytiques lors du traitement du flux de données d’Adobe Analytics. Pour prendre en charge les mises en oeuvre du RGPD, Adobe vous permet de configurer des processus pour le RGPD conformément aux autorisations de votre société, telles qu’établies dans votre accord avec votre Adobe. Voir [Adobe Analytics et le RGPD pour plus d’informations](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=fr).

Le règlement RGPD identifie les rôles et obligations des différentes parties responsables de l’activation en vertu du RGPD (voir [Le RGPD et votre entreprise](https://www.adobe.com/fr/privacy/general-data-protection-regulation.html)).

* Votre entreprise agit comme la variable **contrôleur de données** pour déterminer le contexte et la conservation des données personnelles en fonction de vos besoins et contraintes. Adobe traite et stocke ensuite ces données en votre nom.
* L’Adobe agit comme la variable **responsable du traitement des données** fournir les logiciels et les services nécessaires à la mise en oeuvre des exigences du RGPD en fonction de votre accord avec Adobe.
* Après l’intégration d’un Data Workbench au service RGPD et conformément aux normes du RGPD, les visiteurs sur un site (le **sujets des données**) peuvent exercer leur &quot;droit à l’oubli&quot; par Adobe, le responsable du traitement des données. Pour accomplir le droit à l’oubli, vous, en tant que contrôleur des données, pouvez charger des identifiants visiteur mis en doute pour les Adobe depuis une interface utilisateur ou une API. Voir [Workflow Adobe Analytics RGPD](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) pour plus d’informations, notamment la [envoyer des requêtes d’accès et de suppression](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) .

>[!NOTE]
>
>Pour d’autres sources de données, votre entreprise sera chargée de nettoyer les identifiants visiteur mis en difficulté provenant d’autres sources de journaux, telles que la gestion de la relation client, la point de vente, la reconnaissance graphique et d’autres sources de données brutes. Des modules de services personnalisés de portée seront disponibles pour fournir une assistance aux organisations par _fournissant un ensemble complet de fichiers de remplacement pour chaque source de données ;_ que les conteneurs de service en cours sont requis pour la prise en charge ou la maintenance.

## Mise à niveau de DWB pour la mise en oeuvre du RGPD

Consulting vous conseillera sur le package de services approprié afin de mettre en conformité les implémentations existantes. Pour plus d’informations, contactez votre responsable du succès client.

Si requis:

* [Mise à niveau vers la dernière version](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) de Data Workbench. Pour la sécurité la plus élevée, de nouveaux certificats et de nouvelles fonctionnalités de sécurité ont été ajoutés dans les versions 6.7 du DWB qui sont requises pour l’intégration du RGPD.
* Si vous utilisez des journaux d’événements TSV Analytics hérités, effectuez une mise à niveau vers le [Flux de données Avro](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Si vous utilisez un UCP hérité (Unified Customer Process) avec Transform pour mettre à jour les journaux existants, effectuez une mise à niveau vers le processus en cours. Le processus mis à jour génère directement un fichier de recherche principal pour mapper les identifiants visiteur entre les sources.
* Normalisez le flux de données en fonction du service RGPD.
* Créez un package de services à portée personnalisée pour gérer d’autres sources de journaux telles que la gestion de la relation client, la publication, la réception et d’autres sources de données brutes.
* Confirmez la période de conservation des données par défaut de 25 mois ou plus dans le contrat Analytics.
