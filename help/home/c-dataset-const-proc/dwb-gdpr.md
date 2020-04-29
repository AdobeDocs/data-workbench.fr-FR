---
description: Les outils de données Adobe fournissent des outils et des processus permettant de préparer vos données en vue de les rendre conformes au Règlement général sur la protection des données (RGD).
solution: Analytics
title: Prise en charge des outils de données pour GDPR
topic: Data workbench
translation-type: tm+mt
source-git-commit: 4002d01c4c9aaa7d8833415aba3fa5105cb7ac1f

---


# Prise en charge des outils de données pour GDPR

Les outils de données Adobe fournissent des outils et des processus permettant de préparer vos données pour qu’elles soient conformes au [!DNL General Data Protection Regulations] (RDTD).

Comme toutes les solutions Adobe Analytics, les outils de données prennent en charge le rapport GDPR en , en supprimant et en étiquetant les variables analytiques lors du traitement du flux de données d’Adobe Analytics. Pour prendre en charge les implémentations GDPR, Adobe vous permet de configurer des processus pour GDPR en fonction des autorisations de votre telles qu’elles sont définies dans votre accord avec Adobe. Pour plus d’informations [, voir](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)Adobe Analytics et GDPR.

Le règlement sur le RDPC définit les rôles et les obligations des différentes parties responsables de l&#39;activation du RDPC (voir [RDPC et Votre entreprise](https://www.adobe.com/fr/privacy/general-data-protection-regulation.html)).

* Votre organisation agit comme contrôleur **des** données pour déterminer le contexte et la conservation des données personnelles en fonction de vos besoins et contraintes. Adobe traite et stocke ensuite ces données en votre nom.
* Adobe agit en tant que processeur **de** données pour fournir les logiciels et services nécessaires à la mise en oeuvre des exigences GDPR en fonction de votre accord avec Adobe.
* Après l’intégration des outils de données avec le service GDPR et conformément aux normes GDPR, les d’un site (les sujets **de** données) peuvent exercer leur &quot;droit à l’oubli&quot; par Adobe, le processeur de données. Pour réaliser le droit à l’oubli, vous pouvez, en tant que contrôleur de données, télécharger des ID de contestés vers Adobe à partir d’une interface utilisateur ou d’une API. Voir la documentation [Adobe Analytics GDPR Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) pour en savoir plus, y compris la section [Envoyer les demandes](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) d’accès et de suppression.

>[!NOTE]
>
>Pour d’autres sources de données, votre entreprise sera chargée de nettoyer les ID de contestés provenant d’autres sources de journaux, telles que la gestion de la relation client, la publication de données, la reconnaissance visuelle (IVR) et d’autres sources de données brutes. Des packages de services à portée personnalisée seront disponibles pour fournir une assistance aux entreprises en _fournissant un ensemble complet de fichiers de remplacement pour chaque source_ de données ou d’autres options personnalisées.

## Mise à niveau de DWB pour l’implémentation de GDPR

Le conseil vous conseillera sur le paquet de services approprié pour mettre en conformité les implémentations existantes. Pour plus d’informations, contactez votre responsable de succès client (CSM).

Si requis:

* [Effectuez la mise à niveau vers la dernière version](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) des outils de données. Pour une sécurité maximale, de nouveaux certificats et de nouvelles fonctionnalités de sécurité ont été ajoutés dans les versions DWB 6.7 requises pour l’intégration de GDPR.
* Si vous utilisez des journaux de TSV Analytics hérités, effectuez une mise à niveau vers le flux [de données](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)Avro.
* Si vous utilisez un UCP (Unified Customer Process) hérité avec Transform pour mettre à jour les journaux existants, mettez à niveau vers le processus actuel. Le processus mis à jour génère directement un fichier de recherche maître pour le mappage des ID de entre les sources.
* Normaliser le flux de données pour répondre aux besoins du service GDPR.
* Créez un package de services à portée personnalisée pour gérer d’autres sources de journaux, telles que CRM, POS, IVR et d’autres sources de données brutes.
* Confirmez la période de rétention des données par défaut de 25 mois ou plus dans le contrat Analytics.
