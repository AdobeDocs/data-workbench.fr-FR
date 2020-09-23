---
description: Informations relatives à la surveillance de l’espace de données du événement et à la modification du répertoire des journaux pour les données Sensor.
solution: Analytics
title: Surveillance de l’espace des données d’événement
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# Surveillance de l’espace des données d’événement{#monitoring-event-data-space}

Informations relatives à la surveillance de l’espace de données du événement et à la modification du répertoire des journaux pour les données Sensor.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

[!DNL Insight Server] stocke un fichier journal par [!DNL Sensor] jour sur l’unité de traitement des données ou sur l’unité du serveur de fichiers, selon votre configuration. La taille des fichiers journaux et l’espace d’enregistrement des données requis pour ces derniers dépendent de nombreuses variables, notamment le nombre de sites Web enregistrés et le nombre de requêtes reçues par seconde par vos serveurs Web.

Une installation type de [!DNL Insight Server] (ou d’un [!DNL Insight Server] cluster) est capable de stocker plusieurs téraoctets de données, en supposant que l’implémentation utilise le matériel recommandé par l’Adobe pour les [!DNL Insight Server] machines.

En règle générale, toutes les données du journal restent présentes sur l’ [!DNL Insight Server] ordinateur. S’il devient nécessaire de libérer plus d’espace pour l’enregistrement des données sur l’ordinateur, vous pouvez déplacer tous les fichiers journaux de la journée, sauf les fichiers les plus récents, vers un autre ordinateur ou un autre support d’enregistrement des données (lecteur zip, bande, etc.). Le déplacement des données ne nécessite pas d&#39;arrêt [!DNL Insight Server]et n&#39;affecte pas les fonctionnalités disponibles dans les [!DNL Insights] qui peuvent être connectées [!DNL Insight Server] et fonctionnent avec des données continues. A condition de ne pas traiter ni retraiter un jeu de données d&#39;analyse, vous conservez l&#39;accès à toutes les données précédentes et de nouvelles données restent disponibles dans [!DNL Insight]. Si vous traitez ou retraitez un jeu de données d&#39;analyse, vous ne pouvez pas accéder aux données tant que le traitement n&#39;est pas terminé.

Par défaut, les données de événement produites par [!DNL Sensor] et transmises sont stockées dans le [!DNL Insight Server] dossier du répertoire [!DNL Logs] [!DNL Insight Server] d’installation. Le fichier de configuration Communications, [!DNL Communications.cfg], spécifie l&#39;emplacement des fichiers journaux de données de événement lus par [!DNL Insight Server]les utilisateurs.

**Pour modifier le répertoire de journalisation des[!DNL Sensor]données**

1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône de la [!DNL Insight Server] fenêtre à configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en vue le contenu. Le [!DNL Communications.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche de la colonne du nom *du* serveur [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la [!DNL Communications.cfg] fenêtre, cliquez **[!UICONTROL component]** pour en vue le contenu.
1. Dans la [!DNL Communications.cfg] fenêtre, cliquez **[!UICONTROL Servers]** pour en vue le contenu. Plusieurs types de serveurs peuvent apparaître : Serveurs de fichiers, serveurs de journalisation, serveurs d’initialisation, serveurs d’état, serveurs d’envoi ou serveurs de réplication.
1. Recherchez LoggingServer, où [!DNL Sensor] écrit ses fichiers journaux à traiter par [!DNL Insight Server]et cliquez sur son numéro pour vue au menu.

   ![Infos sur l’étape](assets/cfg_communications_examplevalues_logging.png)

   Le répertoire de journalisation par défaut est le [!DNL Logs] dossier du répertoire [!DNL Insight Server] d’installation.

1. Modifiez le paramètre Répertoire de journaux pour refléter l’emplacement souhaité des fichiers journaux.

   >[!NOTE]
   >
   >Ne modifiez aucun autre paramètre de LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Plusieurs serveurs de fichiers peuvent être répertoriés sous le noeud Serveurs. Vous devrez donc peut-être en vue le contenu de plusieurs d&#39;entre eux (en cliquant sur leur numéro dans la [!DNL Servers] liste) pour trouver le serveur avec un chemin local de journaux\ à modifier.

1. Modifiez le chemin d’accès local pour refléter l’emplacement souhaité des [!DNL .vsl] fichiers.

   >[!NOTE]
   >
   >Ne modifiez aucun autre paramètre du serveur de fichiers.

   Bien que l&#39;emplacement des fichiers journaux ait été modifié dans le [!DNL Communications.cfg] fichier, vous pouvez mapper ces fichiers au répertoire Journaux du [!DNL Server Files Manager] en spécifiant /Logs/ comme URI pour FileServer.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** de la souris en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   1. Dans la [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL Temp] colonne et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

