---
description: Adobe Data Workbench fournit des outils et des processus pour préparer vos données à se conformer au Règlement général sur la protection des données (RGPD).
title: Prise en charge de Data Workbench pour le RGPD
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# Prise en charge de Data Workbench pour le RGPD

Adobe Data Workbench fournit des outils et des processus pour préparer vos données afin de se conformer au [!DNL General Data Protection Regulations] (RGPD).

Comme toutes les solutions Adobe Analytics, Data Workbench prend en charge le RGPD en fournissant le nettoyage, la suppression et l’étiquetage des variables analytiques lors du traitement du flux de données d’Adobe Analytics. Pour prendre en charge les mises en oeuvre du RGPD, Adobe vous permet de configurer des processus pour le RGPD conformément aux autorisations de votre société, telles qu’établies dans votre accord avec votre Adobe. Voir [Adobe Analytics et le RGPD pour plus d’informations](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

Le règlement RGPD identifie les rôles et les obligations des différentes parties responsables de l’activation du RGPD (voir [RGPD et votre entreprise](https://www.adobe.com/fr/privacy/general-data-protection-regulation.html)).

* Votre entreprise agit comme le **contrôleur des données** pour déterminer le contexte et la conservation des données personnelles en fonction de vos besoins et contraintes. Adobe traite et stocke ensuite ces données en votre nom.
* Adobe agit comme le **responsable du traitement des données** pour fournir les logiciels et les services nécessaires à la mise en oeuvre des exigences du RGPD en fonction de votre accord avec l’Adobe.
* Après l’intégration du Data Workbench au service RGPD et conformément aux normes RGPD, les visiteurs sur un site (les **sujets des données**) peuvent exercer leur &quot;droit à l’oubli&quot; par Adobe, l’entité de traitement des données. Pour accomplir le droit à l’oubli, vous, en tant que contrôleur des données, pouvez charger des identifiants visiteur mis en doute pour les Adobe depuis une interface utilisateur ou une API. Pour plus d’informations, notamment la section [Soumettre les demandes d’accès et de suppression](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) , consultez la [documentation relative au processus RGPD d’Adobe Analytics](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) .

>[!NOTE]
>
>Pour d’autres sources de données, votre entreprise sera chargée de nettoyer les identifiants visiteur mis en difficulté provenant d’autres sources de journaux, telles que la gestion de la relation client, la point de vente, la reconnaissance graphique et d’autres sources de données brutes. Les modules de services personnalisés seront disponibles pour fournir une assistance aux organisations en _fournissant un ensemble complet de fichiers de remplacement pour chaque source de données_ que les conteneurs de services en cours doivent prendre en charge ou gérer.

## Mise à niveau de DWB pour la mise en oeuvre du RGPD

Consulting vous conseillera sur le package de services approprié afin de mettre en conformité les implémentations existantes. Pour plus d’informations, contactez votre responsable du succès client.

Si requis:

* [Effectuez une mise à niveau vers la dernière ](https://docs.adobe.com/content/help/fr-FR/data-workbench/using/release-notes/release-notes.html) version de Data Workbench. Pour la sécurité la plus élevée, de nouveaux certificats et de nouvelles fonctionnalités de sécurité ont été ajoutés dans les versions 6.7 du DWB qui sont requises pour l’intégration du RGPD.
* Si vous utilisez des journaux d’événements TSV Analytics hérités, effectuez une mise à niveau vers le [flux de données Avro](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Si vous utilisez un UCP hérité (Unified Customer Process) avec Transform pour mettre à jour les journaux existants, effectuez une mise à niveau vers le processus en cours. Le processus mis à jour génère directement un fichier de recherche principal pour mapper les identifiants visiteur entre les sources.
* Normalisez le flux de données en fonction du service RGPD.
* Créez un package de services à portée personnalisée pour gérer d’autres sources de journaux telles que la gestion de la relation client, la publication, la réception et d’autres sources de données brutes.
* Confirmez la période de conservation des données par défaut de 25 mois ou plus dans le contrat Analytics.
