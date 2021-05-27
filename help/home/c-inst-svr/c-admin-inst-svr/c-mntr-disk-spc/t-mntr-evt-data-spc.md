---
description: Informations sur la surveillance de l’espace de données d’événement et la modification du répertoire de journal des données de Capteur.
title: Surveillance de l’espace des données d’événement
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Surveillance de l’espace des données d’événement{#monitoring-event-data-space}

Informations sur la surveillance de l’espace de données d’événement et la modification du répertoire de journal des données de Capteur.

**Fréquence recommandée :** Toutes les 5-10 minutes

[!DNL Insight Server] stocke un fichier journal par  [!DNL Sensor] jour sur l’unité de traitement des données ou l’unité du serveur de fichiers, selon votre configuration. La taille des fichiers journaux et la quantité d’espace de stockage des données qui y est nécessaire dépendent de nombreuses variables, notamment le nombre de sites Web consignés et le nombre de demandes que vos serveurs web reçoivent par seconde.

Une installation type de [!DNL Insight Server] (ou d’une grappe [!DNL Insight Server]) est capable de stocker plusieurs téraoctets de données, en supposant que l’implémentation utilise le matériel recommandé par Adobe pour la ou les machines [!DNL Insight Server].

En règle générale, toutes les données de journal restent présentes sur la machine [!DNL Insight Server]. S’il devient nécessaire de libérer plus d’espace de stockage de données sur l’ordinateur, vous pouvez déplacer tous les fichiers journaux de la journée la plus récente, à l’exception de ceux du jour le plus récent, vers un autre ordinateur ou support de stockage de données (lecteur compressé, bande passante, etc.). Le déplacement des données n’exige pas que vous arrêtiez [!DNL Insight Server] et cela n’affecte pas la fonctionnalité disponible dans les [!DNL Insights] qui peuvent être connectées à [!DNL Insight Server] et l’utilisation de données continues. Si vous ne traitez pas ou ne retraitez pas un jeu de données d’analyse, vous conservez l’accès à toutes les données précédentes et de nouvelles données restent disponibles dans [!DNL Insight]. Si vous traitez ou retraitez un jeu de données d’analyse, vous ne pouvez pas accéder aux données tant que le traitement n’est pas terminé.

Par défaut, les données d’événement produites par [!DNL Sensor] et transmises à [!DNL Insight Server] sont stockées dans le dossier [!DNL Logs] du répertoire d’installation [!DNL Insight Server]. Le fichier de configuration des communications, [!DNL Communications.cfg], spécifie l’emplacement des fichiers journaux de données d’événement lus par [!DNL Insight Server].

**Pour modifier le répertoire des journaux des  [!DNL Sensor] données**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône [!DNL Insight Server] que vous souhaitez configurer, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la balise [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en visualiser le contenu. Le fichier [!DNL Communications.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit sur la coche dans la colonne *nom du serveur* pour [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche s’affiche dans la colonne [!DNL Temp] pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL component]** pour en visualiser le contenu.
1. Dans la fenêtre [!DNL Communications.cfg], cliquez sur **[!UICONTROL Servers]** pour en visualiser le contenu. Plusieurs types de serveurs peuvent apparaître : Serveurs de fichiers, serveurs de journalisation, serveurs Init, serveurs d’état, serveurs d’envoi ou serveurs de réplication.
1. Recherchez LoggingServer, où [!DNL Sensor] écrit ses fichiers journaux à traiter par [!DNL Insight Server], puis cliquez sur son numéro pour afficher le menu.

   ![Infos sur l’étape](assets/cfg_communications_examplevalues_logging.png)

   Le répertoire de journal par défaut est le dossier [!DNL Logs] dans le répertoire d’installation de [!DNL Insight Server].

1. Modifiez le paramètre Répertoire des journaux pour refléter l’emplacement souhaité des fichiers journaux.

   >[!NOTE]
   >
   >Ne modifiez aucun autre paramètre pour LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Plusieurs FileServers peuvent être répertoriés sous le noeud Servers. Vous devrez donc peut-être consulter le contenu de plusieurs d’entre eux (en cliquant sur leurs numéros dans la liste [!DNL Servers]) pour trouver le serveur avec un Chemin d’accès local des journaux\ à modifier.

1. Modifiez le chemin d’accès local pour refléter l’emplacement souhaité des fichiers [!DNL .vsl].

   >[!NOTE]
   >
   >Ne modifiez aucun autre paramètre pour FileServer.

   Bien que l’emplacement des fichiers journaux ait été modifié dans le fichier [!DNL Communications.cfg] , vous pouvez les mapper au répertoire Journaux de [!DNL Server Files Manager] en spécifiant /Logs/ comme URI pour FileServer.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans la balise [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
