---
description: Informations sur la surveillance de l’espace de données d’événement et la modification du répertoire de journal des données de Capteur.
title: Surveillance de l’espace des données d’événement
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Surveillance de l’espace des données d’événement{#monitoring-event-data-space}

{{eol}}

Informations sur la surveillance de l’espace de données d’événement et la modification du répertoire de journal des données de Capteur.

**Fréquence recommandée :** Toutes les 5-10 minutes

[!DNL Insight Server] stocke un fichier journal par [!DNL Sensor] chaque jour, soit l’unité de traitement des données, soit l’unité du serveur de fichiers, selon votre configuration. La taille des fichiers journaux et la quantité d’espace de stockage des données qui y est nécessaire dépendent de nombreuses variables, notamment le nombre de sites Web consignés et le nombre de demandes que vos serveurs web reçoivent par seconde.

Une installation standard de [!DNL Insight Server] (ou un [!DNL Insight Server] (grappe) peut stocker plusieurs téraoctets de données, en supposant que l’implémentation utilise le matériel recommandé par Adobe pour la variable [!DNL Insight Server] machines.

En règle générale, toutes les données de journal restent présentes sur la variable [!DNL Insight Server] machine. S’il devient nécessaire de libérer plus d’espace de stockage de données sur l’ordinateur, vous pouvez déplacer tous les fichiers journaux de la journée la plus récente, à l’exception de ceux du jour le plus récent, vers un autre ordinateur ou support de stockage de données (lecteur compressé, bande passante, etc.). Le déplacement des données ne nécessite pas d’arrêter [!DNL Insight Server], et cela n’affecte pas la fonctionnalité disponible dans les [!DNL Insights] qui peut être connecté à [!DNL Insight Server] et l’utilisation de données continues. Si vous ne traitez pas ou ne retraitez pas un jeu de données d’analyse, vous conservez l’accès à toutes les données précédentes et de nouvelles données restent disponibles dans [!DNL Insight]. Si vous traitez ou retraitez un jeu de données d’analyse, vous ne pouvez pas accéder aux données tant que le traitement n’est pas terminé.

Par défaut, les données d’événement générées par [!DNL Sensor] et transmis à [!DNL Insight Server] est stocké dans la variable [!DNL Logs] dans le dossier [!DNL Insight Server] répertoire d’installation. Le fichier de configuration des communications, [!DNL Communications.cfg], spécifie l’emplacement des fichiers journaux de données d’événement lus par [!DNL Insight Server].

**Pour modifier le répertoire des journaux pour [!DNL Sensor] data**

1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Communications.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Communications.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Communications.cfg].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Dans le [!DNL Communications.cfg] fenêtre, cliquez sur **[!UICONTROL component]** pour afficher son contenu.
1. Dans le [!DNL Communications.cfg] fenêtre, cliquez sur **[!UICONTROL Servers]** pour afficher son contenu. Plusieurs types de serveurs peuvent apparaître : Serveurs de fichiers, serveurs de journalisation, serveurs Init, serveurs d’état, serveurs d’envoi ou serveurs de réplication.
1. Recherchez LoggingServer, qui est l’emplacement où [!DNL Sensor] écrit ses fichiers journaux à traiter par [!DNL Insight Server], puis cliquez sur son numéro pour afficher le menu.

   ![Infos sur l’étape](assets/cfg_communications_examplevalues_logging.png)

   Le répertoire de journal par défaut est le suivant : [!DNL Logs] dans le dossier [!DNL Insight Server] répertoire d’installation.

1. Modifiez le paramètre Répertoire des journaux pour refléter l’emplacement souhaité des fichiers journaux.

   >[!NOTE]
   >
   >Ne modifiez aucun autre paramètre pour LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Plusieurs FileServers peuvent être répertoriés sous le noeud Servers. Il se peut donc que vous deviez consulter le contenu de plusieurs d’entre eux (en cliquant sur leur numéro dans la variable [!DNL Servers] ) pour trouver le serveur avec un chemin d’accès local des journaux à modifier.

1. Modifiez le chemin d’accès local pour refléter l’emplacement souhaité de la [!DNL .vsl] fichiers .

   >[!NOTE]
   >
   >Ne modifiez aucun autre paramètre pour FileServer.

   Bien que l’emplacement des fichiers journaux ait été modifié dans la variable [!DNL Communications.cfg] vous pouvez mapper ces fichiers au répertoire Journaux de la variable [!DNL Server Files Manager] en spécifiant /Logs/ comme URI pour FileServer.

1. Enregistrez vos modifications sur le serveur en procédant comme suit :

   1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

   1. Dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL Temp] et sélectionnez **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
