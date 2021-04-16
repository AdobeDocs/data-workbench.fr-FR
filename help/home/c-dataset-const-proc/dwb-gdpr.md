---
description: Adobe Data Workbench fournit des outils et des processus pour préparer vos données en conformité avec le Règlement général sur la protection des données (RGPD).
title: Prise en charge de Data Workbench pour le RGPD
exl-id: fdc43567-0c57-4851-9073-e295258a8074
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# Prise en charge de Data Workbench pour le RGPD

Adobe Data Workbench fournit des outils et des processus permettant de préparer vos données pour se conformer au [!DNL General Data Protection Regulations] (RGPD).

Comme toutes les solutions Adobe Analytics, Data Workbench fournit une prise en charge de GDPR en fournissant le cleansing, la suppression et l&#39;étiquetage des variables analytiques lors du traitement du flux de données Adobe Analytics. Pour prendre en charge les mises en oeuvre des RGD, l’Adobe vous permet de configurer des processus pour RGD en fonction des autorisations de votre société, telles que définies dans votre accord avec l’Adobe. Voir [Adobe Analytics et GDPR pour plus d&#39;informations](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

Le règlement sur les RGD identifie les rôles et obligations des différentes parties responsables de l&#39;activation des RGD (voir [RGD et Votre entreprise](https://www.adobe.com/fr/privacy/general-data-protection-regulation.html)).

* Votre organisation agit en tant que **contrôleur de données** pour déterminer le contexte et la conservation des données personnelles en fonction de vos besoins et contraintes. Adobe traite et stocke ensuite ces données en votre nom.
* L&#39;Adobe agit en tant que **processeur de données** pour fournir les logiciels et les services nécessaires à la mise en oeuvre des exigences du RGPD en fonction de votre accord avec l&#39;Adobe.
* Après l&#39;intégration d&#39;un Data Workbench au service GDPR et conformément aux normes GDPR, les visiteurs sur un site (les **sujets de données**) peuvent exercer leur &quot;droit à l&#39;oubli&quot; par l&#39;Adobe, le processeur de données. Pour réaliser le droit à l’oubli, vous, en tant que contrôleur de données, pouvez télécharger des ID de visiteur contestés vers l’Adobe à partir d’une interface utilisateur ou d’une API. Pour plus d&#39;informations, notamment la section [Envoi des demandes d&#39;accès et de suppression](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html), consultez la documentation [Processus de traitement global de documents d&#39;Adobe Analytics](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html).

>[!NOTE]
>
>Pour d’autres sources de données, votre entreprise sera chargée de nettoyer les ID de visiteur contestés provenant d’autres sources de journaux, telles que la gestion de la relation client, le PDV, l’IVR et d’autres sources de données brutes. Des packages de services à portée personnalisée seront disponibles pour fournir une assistance aux entreprises en _fournissant un ensemble complet de fichiers de remplacement pour chaque source de données_ que les conteneurs de services en cours doivent prendre en charge ou gérer.

## Mise à niveau de DWB pour la mise en oeuvre du RGPD

Consulting vous conseillera sur les services appropriés pour mettre en conformité les implémentations existantes. Pour plus d’informations, contactez votre responsable de succès client.

Si requis:

* [Effectuez une mise à niveau vers la dernière ](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/release-notes/release-notes.html) version de Data Workbench. Pour une sécurité maximale, de nouveaux certificats et de nouvelles fonctionnalités de sécurité ont été ajoutés dans les versions DWB 6.7 qui sont requises pour l’intégration de GDPR.
* Si vous utilisez des journaux de événement TSV Analytics hérités, effectuez une mise à niveau vers le [flux de données Avro](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Si vous utilisez un UCP (Unified Customer Process) hérité avec Transform pour mettre à jour les journaux existants, mettez à niveau vers le processus actuel. Le processus mis à jour génère directement un fichier de recherche principal pour le mappage des ID de visiteur entre les sources.
* Normaliser le flux de données en fonction du service RMMD.
* Créez un package de services à portée personnalisée pour gérer d’autres sources de journaux, telles que la gestion de la relation client, la déclaration de situation géographique, la reconnaissance visuelle et d’autres sources de données brutes.
* Confirmez la période de rétention des données par défaut de 25 mois ou plus dans le contrat Analytics.
