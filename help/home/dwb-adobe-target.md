---
description: Intégrer le Data Workbench à Adobe Target. Exportez les segments de données et renseignez automatiquement les fichiers d’exportation.
title: Intégration de Data Workbench avec Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Intégration de Data Workbench avec Adobe Target

L’intégration d’un Data Workbench d’Adobe à Adobe Target est devenue plus facile grâce aux fonctions de Data Workbench pour exporter les segments de données et renseigner automatiquement les fichiers d’exportation.

Adobe Data Workbench offre une intégration en boucle fermée avec Adobe Target pour le partage de données et la génération de rapports. Dans le Data Workbench, vous pouvez analyser les populations à la recherche de segments significatifs à l’aide de toutes les données disponibles, y compris les conversions hors ligne par le biais de canaux tels que le téléphone, un magasin, etc.

Par exemple, un visiteur recherche des chaussures sur votre site Web mais ne les convertit pas. Au contraire, le visiteur télécharge un coupon pour 20 % de son prochain achat, puis achète une chemise dans votre magasin. En utilisant Data Workbench, vous pouvez rassembler ces données, puis les renvoyer à la Cible pour indiquer que le visiteur a acheté une chemise hors ligne. Vous pouvez ensuite cible une campagne offrant une cravate à ce visiteur, alors que normalement la Cible peut essayer de relancer les chaussures sur ce visiteur.

## Configurer un Data Workbench avec Adobe Target

1. Cliquez avec le bouton droit sur l&#39;en-tête dans la fenêtre [!UICONTROL Detail Table].

   ![](assets/insight-to-tnt.png)

1. Sélectionnez **[!UICONTROL New Target Export]** et saisissez le nom d&#39;un nouveau fichier d&#39;exportation sous la commande **[!UICONTROL Save As]** du menu.

1. Cliquez sur **[!UICONTROL Save Export File]**.

   Une fenêtre de modèle d’exportation s’ouvre.

   Toutes les informations Adobe Target sont renseignées automatiquement. Il crée la liste des paramètres en fonction de ce que vous avez placé dans l’exportation de segments. Une fois terminé, le Data Workbench envoie les données au serveur Adobe Target.

   **Remarque :** Le fichier de modèle doit être configuré par le  [!UICONTROL Profile Architect]. Les [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] et [!UICONTROL Mbox Name] doivent être saisis. Si vous avez plusieurs sites, remplissez plusieurs modèles et enregistrez-les sur le serveur. Les modèles de Profil Manager se trouvent dans `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Spécifiez le paramètre de requête [!UICONTROL mboxPC].

   Si le nom de l’attribut de Data Workbench est différent de [!UICONTROL mboxPC], vous devez modifier le paramètre de Requête approprié et le renommer en _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Lorsque vous enregistrez le fichier d’exportation sur le serveur, l’exportation démarre. Une fois l&#39;application [!UICONTROL TnTSend.exe] terminée, elle démarre et commence à envoyer des données au compte de Cible.

## Configuration du Data Workbench pour la Cible

Renseignez les tâches suivantes dans Adobe Target :

Data Workbench transmet les profils d&#39;utilisateur à Adobe Target. Pour configurer l&#39;exportation vers la Cible, vous devez configurer et activer son API et fournir les paramètres **[!UICONTROL clientname]** et **[!UICONTROL domain postfix]** pour le fichier de configuration d&#39;exportation (`export.cfg`).

Une nouvelle option booléenne appelée **[!UICONTROL Oneshot]** a été ajoutée aux fichiers d’exportation de segments. Cette option est incluse dans le fichier de modèle distribué avec le nouveau profil. Si [!UICONTROL Oneshot] est défini sur _true_, le fichier `.export` sera renommé `.export.done-TIMESTAMP` une fois l’exportation terminée, ce qui garantit que le segment ne sera jamais exporté plusieurs fois. Ceci est important lors de l’exportation vers Adobe Target.

**Remarque :** Un appel d’un Data Workbench à Adobe Target est comptabilisé comme un  [!UICONTROL mbox] appel, nécessitant un appel pour chaque profil envoyé. Par conséquent, les coûts augmentent si plusieurs appels sont nécessaires entre les deux solutions.

Une configuration incomplète génère le message d’erreur suivant dans le journal :

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configuration de Adobe Target pour Data Workbench

Dans Adobe Target, aucune configuration spéciale n’est nécessaire pour qu’un client puisse envoyer des données de profil. Les informations de profil d&#39;un utilisateur sont généralement transmises dans la demande [!UICONTROL mbox] régulière et les serveurs mettent les paramètres de profil à disposition pour une configuration de campagne ciblée en tant que fonctionnalité standard sans configuration supplémentaire.

Adobe Target intègre une intégration de Data Workbench, qui peut être activée à partir de la page Détails du client de super-utilisateur. L’activation de l’option repositionnera les segments qui sont partagés à partir de l’Data Workbench dans Adobe Target afin de les rendre disponibles pour le ciblage.

## Définition du rapports de journal HTTP dans le fichier ExportIntegration.exe

Réduisez le rapports long à [!UICONTROL HTTP.log] lorsque vous utilisez [!UICONTROL ExportIntegration.exe] pour exporter des fichiers d’intégration Adobe Target.

Un nouveau fichier de configuration [!UICONTROL httpLoggingEI.cfg] (situé à `server\Admin\Export\httpLoggingEI.cfg`) permet de réduire la journalisation détaillée au fichier [!UICONTROL HTTP.log] lors de l&#39;exportation de données à l&#39;aide de [!UICONTROL ExportIntegration.exe]. Cela vous permet d’arrêter la journalisation détaillée des demandes/réponses.

La journalisation détaillée est déjà capturée dans des fichiers [!UICONTROL TnTSend.log].

__ Truesets verbose logging, et  __ Falsestops verbose logging to  [!UICONTROL HTTP.log] file.

Dans le paramètre False, seul un message d’avertissement est envoyé au fichier [!UICONTROL HTTP.log] (Contenu d’information non envoyé).
