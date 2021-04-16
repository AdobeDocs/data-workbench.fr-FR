---
description: Procédure d’installation des composants Microsoft requis.
title: Installation des composants obligatoires
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
translation-type: tm+mt
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
   >Ceci ne doit être installé qu&#39;après avoir installé et configuré le rôle Web IIS.

1. Suivez l’assistant et choisissez les valeurs par défaut lorsque vous êtes invité à terminer l’installation.
1. Une fois installé, vérifiez que le pool d&#39;applications ASP.NET v.4.0 a été ajouté dans la liste **[!UICONTROL Application Pools]** dans IIS.
1. Installez la base de données Microsoft SQL Server.

   Utilisez toute version de SQL Server 2008 ou 2008 R2 (Express est pris en charge) avec les outils de gestion (l&#39;Adobe recommande SQL Server 2008 R2 SP1 - Express Edition). 1. Pour une installation générique sans instances SQL Server existantes s&#39;exécutant à l&#39;avance, sélectionnez l&#39;option **[!UICONTROL Default Instance]** dans l&#39;écran **[!UICONTROL Instance Configuration]**.
1. Pour le reste des options de configuration, suivez l’assistant et choisissez les valeurs par défaut lorsque vous êtes invité à terminer l’installation.
1. Installez Microsoft Web Deploy v2.0.

   Pour la plupart des installations, l&#39;installation de **[!UICONTROL Typical]** est correcte. Si, toutefois, vous prévoyez d&#39;effectuer des déploiements à distance, vous devrez effectuer une installation complète (sélectionnez **[!UICONTROL Complete]**).

   Une fois que toutes les conditions préalables sont correctement installées, vous êtes prêt à préparer les serveurs des outils de données à communiquer avec le tableau de bord.
