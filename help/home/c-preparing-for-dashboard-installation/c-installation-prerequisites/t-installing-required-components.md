---
description: Procédure d’installation des composants Microsoft requis.
title: Installation des composants obligatoires
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Installation des composants obligatoires{#installing-required-components}

Procédure d’installation des composants Microsoft requis.

1. Installez Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Cette opération ne doit être installée qu&#39;après l&#39;installation et la configuration du rôle Web IIS.

1. Suivez l’assistant et choisissez les valeurs par défaut à utiliser pour terminer l’installation.
1. Une fois installé, vérifiez que le pool d’applications ASP.NET v.4.0 a été ajouté à la liste **[!UICONTROL Application Pools]** dans IIS.
1. Installez la base de données Microsoft SQL Server.

   Utilisez n’importe quelle version de SQL Server 2008 ou 2008 R2 (Express est pris en charge) avec les outils de gestion (Adobe recommande SQL Server 2008 R2 SP1 - Express Edition). 1. Pour une installation générique sans instances SQL Server existantes s&#39;exécutant à l&#39;avance, sélectionnez l&#39;option **[!UICONTROL Default Instance]** dans l&#39;écran **[!UICONTROL Instance Configuration]**.
1. Pour le reste des options de configuration, suivez l’assistant et choisissez les valeurs par défaut lorsque vous êtes invité à terminer l’installation.
1. Installez Microsoft Web Deploy v2.0.

   Pour la plupart des installations, l’installation de **[!UICONTROL Typical]** est correcte. Si, toutefois, vous prévoyez d’effectuer des déploiements distants, vous devrez effectuer une installation complète (choisissez **[!UICONTROL Complete]**).

   Une fois que toutes les conditions préalables sont correctement installées, vous êtes prêt à préparer les serveurs Data Workbench pour communiquer avec le tableau de bord.
