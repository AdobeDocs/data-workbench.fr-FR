---
description: Procédure d’installation des composants Microsoft requis.
solution: Analytics
title: Installation des composants requis
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installation des composants requis{#installing-required-components}

Procédure d’installation des composants Microsoft requis.

1. Installez Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Cette opération ne doit être installée qu&#39;après l&#39;installation et la configuration du rôle Web IIS.

1. Suivez l’assistant et choisissez les valeurs par défaut lorsque vous êtes invité à terminer l’installation.
1. Une fois installé, vérifiez que le pool d&#39;applications ASP.NET v.4.0 a été ajouté dans la **[!UICONTROL Application Pools]** liste dans IIS.
1. Installez la base de données Microsoft SQL Server.

   Utilisez toute version de SQL Server 2008 ou 2008 R2 (Express est pris en charge) avec les outils de gestion (Adobe recommande SQL Server 2008 R2 SP1 - Express Edition). 1. Pour une installation générique sans instances SQL Server existantes s&#39;exécutant à l&#39;avance, sélectionnez l&#39; **[!UICONTROL Default Instance]** option à l&#39; **[!UICONTROL Instance Configuration]** écran.
1. Pour le reste des options de configuration, suivez l’assistant et choisissez les valeurs par défaut lorsque vous êtes invité à terminer l’installation.
1. Installez Microsoft Web Deploy v2.0.

   Pour la plupart des installations, l’ **[!UICONTROL Typical]** installation est correcte. Si, toutefois, vous prévoyez d’effectuer des déploiements à distance, vous devrez effectuer une installation complète (sélectionnez **[!UICONTROL Complete]**).

   Une fois que toutes les conditions préalables sont correctement installées, vous êtes prêt à préparer les serveurs de l’outil de données à communiquer avec le tableau de bord.
