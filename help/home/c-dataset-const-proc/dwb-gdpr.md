---
description: Adobe Data Workbench fournit des outils et des processus permettant de préparer vos données en conformité avec le Règlement général sur la protection des données (RGPD).
solution: Analytics
title: Prise en charge des outils de données pour GDPR
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---


# Prise en charge des outils de données pour GDPR

Adobe Data Workbench fournit des outils et des processus permettant de préparer vos données en vue de les mettre en conformité avec le [!DNL General Data Protection Regulations] (RGPD).

Comme toutes les solutions Adobe Analytics, les outils de données prennent en charge GDPR en fournissant le cleansing, la suppression et l’étiquetage des variables analytiques lors du traitement du flux de données Adobe Analytics. Pour prendre en charge les mises en oeuvre de RGMD, Adobe vous permet de configurer des processus pour RGMD en fonction des autorisations de votre société, telles que définies dans votre accord avec Adobe. Pour plus d’informations [, voir](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)Adobe Analytics et GDPR.

Le règlement sur les RGD identifie les rôles et les obligations des différentes parties responsables de l&#39;activation des RGD (voir [RGD et Votre entreprise](https://www.adobe.com/fr/privacy/general-data-protection-regulation.html)).

* Votre organisation agit en tant que contrôleur **** de données pour déterminer le contexte et la conservation des données personnelles en fonction de vos besoins et contraintes. Adobe traite et stocke ensuite ces données en votre nom.
* Adobe agit comme processeur **de** données pour fournir les logiciels et les services nécessaires à la mise en oeuvre des exigences du RGPD en fonction de votre accord avec Adobe.
* Après l&#39;intégration des outils de données au service RMPE et conformément aux normes RMPE, les visiteurs sur un site (les personnes **concernées par les** données) peuvent exercer leur &quot;droit à l&#39;oubli&quot; par Adobe, le processeur de données. Pour accomplir le droit à l’oubli, vous, en tant que contrôleur de données, pouvez télécharger des ID de visiteur contestés vers Adobe à partir d’une interface utilisateur ou d’une API. Pour plus d’informations, notamment sur la section [Envoyer l’accès et supprimer des requêtes](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) , consultez la documentation relative au flux de travail [GDPR d’](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) Adobe Analytics.

>[!NOTE]
>
>Pour d’autres sources de données, votre entreprise sera chargée de nettoyer les ID de visiteur contestés provenant d’autres sources de journaux, telles que la gestion de la relation client, le PDV, l’IVR et d’autres sources de données brutes. Des packs de services à portée personnalisée seront disponibles pour fournir une assistance aux entreprises en _fournissant un ensemble complet de fichiers de remplacement pour chaque source_ de données que les responsables du service en cours doivent prendre en charge ou gérer.

## Mise à niveau de DWB pour la mise en oeuvre du RGPD

Consulting vous conseillera sur les services appropriés pour mettre en conformité les implémentations existantes. Pour plus d’informations, contactez votre responsable de succès client.

Si requis:

* [Effectuez la mise à niveau vers la dernière version](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/release-notes/release-notes.translate.html) des outils de données. Pour une sécurité maximale, de nouveaux certificats et de nouvelles fonctionnalités de sécurité ont été ajoutés dans les versions DWB 6.7 qui sont requises pour l’intégration de GDPR.
* Si vous utilisez des journaux de événement TSV Analytics hérités, effectuez une mise à niveau vers le flux [de données](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)Avro.
* Si vous utilisez un UCP (Unified Customer Process) hérité avec Transform pour mettre à jour les journaux existants, mettez à niveau vers le processus actuel. Le processus mis à jour génère directement un fichier de recherche principal pour le mappage des ID de visiteur entre les sources.
* Normaliser le flux de données en fonction du service RMMD.
* Créez un package de services à portée personnalisée pour gérer d’autres sources de journaux, telles que la gestion de la relation client, la déclaration de situation géographique, la reconnaissance visuelle et d’autres sources de données brutes.
* Confirmez la période de rétention des données par défaut de 25 mois ou plus dans le contrat Analytics.
