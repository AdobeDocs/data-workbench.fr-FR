---
description: Intégration des outils de données à Adobe Target. Exportez les segments de données et renseignez automatiquement les fichiers d’exportation.
solution: Analytics
title: Intégration des outils de données à Adobe Target
topic: Data workbench
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Intégration des outils de données à Adobe Target

L’intégration des outils de données Adobe à Adobe Target est devenue plus facile avec les fonctionnalités des outils de données pour exporter des segments de données et renseigner automatiquement les fichiers d’exportation.

Les outils de données Adobe fournissent une intégration en boucle fermée avec Adobe Target pour le partage de données et la génération de rapports. Dans les Outils de données, vous pouvez analyser les populations à la recherche de segments significatifs à l’aide de toutes les données disponibles, y compris les conversions hors ligne par le biais de canaux tels que le téléphone, un magasin, etc.

Par exemple, un visiteur recherche des chaussures sur votre site Web mais ne les convertit pas. Le visiteur télécharge plutôt un bon pour 20 % de son prochain achat, puis achète une chemise dans votre boutique. Les outils de données vous permettent de rassembler ces données, puis de transmettre ces données de profil à Target pour vous montrer que le visiteur a acheté une chemise hors ligne. Vous pouvez ensuite cibler une campagne proposant une cravate à ce visiteur, alors que Target tente normalement de lui proposer à nouveau des chaussures.

## Configuration des outils de données avec Adobe Target

1. Cliquez avec le bouton droit sur l’en-tête dans la [!UICONTROL Detail Table] fenêtre.

   ![](assets/insight-to-tnt.png)

1. Sélectionnez **[!UICONTROL New Target Export]** et saisissez le nom d’un nouveau fichier d’exportation sous la **[!UICONTROL Save As]** commande du menu.

1. Cliquez sur **[!UICONTROL Save Export File]**.

   Une fenêtre de modèle d’exportation s’ouvre.

   Toutes les informations Adobe Target sont renseignées automatiquement. Il crée la liste des paramètres en fonction de ce que vous avez mis dans l’exportation de segments. Une fois l’opération terminée, les outils de données envoient les données au serveur Adobe Target.

   **Remarque :** Le fichier de modèle doit être configuré par le [!UICONTROL Profile Architect]. Le [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]et [!UICONTROL Mbox Name] doit être entré. Si vous avez plusieurs sites, remplissez plusieurs modèles et enregistrez-les sur le serveur. Les modèles du Gestionnaire de profils se trouvent dans `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Spécifiez le paramètre de [!UICONTROL mboxPC] requête.

   Si le nom de l’attribut Outils de données n’est pas [!UICONTROL mboxPC], vous devez modifier le paramètre de requête approprié et le renommer en _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Lorsque vous enregistrez le fichier d’exportation sur le serveur, l’exportation commence. Une fois l’ [!UICONTROL TnTSend.exe] application terminée, elle démarre et commence à envoyer des données au compte Target.

## Configuration des outils de données pour Target

Effectuez les tâches suivantes dans Adobe Target :

Les outils de données transmettent les profils utilisateur à Adobe Target. Pour effectuer la configuration en vue de l’exportation vers Target, vous devez configurer et activer son API et fournir les paramètres **[!UICONTROL clientname]** et **[!UICONTROL domain postfix]** du fichier de configuration d’exportation (`export.cfg`).

Une nouvelle option booléenne nommée **[!UICONTROL Oneshot]** a été ajoutée aux fichiers d’exportation de segments. Cette option est incluse dans le fichier de modèle distribué avec le nouveau profil. Si [!UICONTROL Oneshot] est défini sur _true_, le `.export` fichier sera renommé en `.export.done-TIMESTAMP` une fois l’exportation terminée, ce qui garantit que le segment ne sera jamais exporté plus d’une fois. Cela est important lors de l’exportation vers Adobe Target.

**Remarque :** Un appel des outils de données vers Adobe Target est comptabilisé comme un [!UICONTROL mbox] appel, nécessitant un appel pour chaque profil envoyé. Par conséquent, les coûts augmentent si plusieurs appels sont nécessaires entre les deux solutions.

Une configuration incomplète génère le message d’erreur suivant dans le journal :

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configuration d’Adobe Target pour les outils de données

Dans Adobe Target, aucune configuration spéciale n’est nécessaire pour qu’un client envoie des données de profil. Les informations de profil d’un utilisateur sont généralement transmises dans la [!UICONTROL mbox] requête régulière et les serveurs rendent les paramètres de profil disponibles pour une configuration de campagne ciblée en tant que fonctionnalité standard sans configuration supplémentaire.

L’intégration des outils de données d’Adobe Target est intégrée. Elle peut être activée à partir de la page Détails du client super-utilisateur. L’activation de l’option représentera les segments partagés à partir des outils de données dans Adobe Target afin de les rendre disponibles pour le ciblage.

## Définition de la création de rapports de journal HTTP dans ExportIntegration.exe

Réduisez la création de rapports longs à [!UICONTROL HTTP.log] l’utilisation [!UICONTROL ExportIntegration.exe] pour exporter des fichiers d’intégration Adobe Target.

Un nouveau fichier [!UICONTROL httpLoggingEI.cfg] de configuration (situé à `server\Admin\Export\httpLoggingEI.cfg`) permet de réduire la journalisation détaillée dans le [!UICONTROL HTTP.log] fichier pour l’exportation de données à l’aide de [!UICONTROL ExportIntegration.exe]. Cela vous permet d’arrêter la journalisation détaillée des requêtes/réponses.

La journalisation détaillée est déjà capturée dans [!UICONTROL TnTSend.log] des fichiers.

_True_ définit la journalisation détaillée et _False_ arrête la journalisation détaillée dans [!UICONTROL HTTP.log] le fichier.

Dans le paramètre False, seul un message d’avertissement est envoyé au [!UICONTROL HTTP.log] fichier (contenu Info non envoyé).