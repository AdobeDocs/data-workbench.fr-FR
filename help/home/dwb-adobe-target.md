---
description: Intégration du Data Workbench à Adobe Target. Exportez des segments de données et renseignez automatiquement les fichiers d’exportation.
title: Intégration de Data Workbench avec Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Intégration de Data Workbench avec Adobe Target

{{eol}}

L’intégration d’Adobe Data Workbench à Adobe Target est devenue plus facile avec les fonctionnalités de Data Workbench permettant d’exporter des segments de données et de renseigner automatiquement les fichiers d’exportation.

Adobe Data Workbench fournit une intégration en boucle fermée avec Adobe Target pour le partage de données et la génération de rapports. Dans Data Workbench, vous pouvez analyser les populations à la recherche de segments significatifs à l’aide de toutes les données disponibles, y compris les conversions hors ligne par le biais de canaux tels que le téléphone, un magasin, etc.

Par exemple, un visiteur recherche des chaussures sur votre site web, mais ne procède pas à la conversion. Le visiteur télécharge plutôt un coupon pour 20 % de son prochain achat, puis achète une chemise dans votre boutique. Avec Data Workbench, vous pouvez rassembler ces données, puis renvoyer ces données de profil à Target pour indiquer que le visiteur a acheté une chemise hors ligne. Vous pouvez ensuite cibler une campagne proposant une cravate à ce visiteur, alors que Target tente normalement de lui reproposer des chaussures.

## Configuration d’un Data Workbench avec Adobe Target

1. Cliquez avec le bouton droit sur l’en-tête dans la [!UICONTROL Detail Table] fenêtre.

   ![](assets/insight-to-tnt.png)

1. Sélectionner **[!UICONTROL New Target Export]** et saisissez le nom d’un nouveau fichier d’exportation sous le champ **[!UICONTROL Save As]** dans le menu.

1. Cliquez sur **[!UICONTROL Save Export File]**.

   Une fenêtre de modèle d&#39;export s&#39;ouvre.

   Toutes les informations Adobe Target sont renseignées automatiquement. Il crée la liste des paramètres en fonction de ce que vous avez placé dans l’exportation de segments. Une fois l’opération terminée, Data Workbench envoie les données au serveur Adobe Target.

   **Remarque :** Le fichier de modèle doit être configuré par la variable [!UICONTROL Profile Architect]. Le [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host], et [!UICONTROL Mbox Name] doivent être saisies. Si vous disposez de plusieurs sites, remplissez plusieurs modèles et enregistrez-les sur le serveur. Les modèles de Profile Manager se trouvent dans `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Spécifiez la variable [!UICONTROL mboxPC] paramètre de requête.

   Si le nom de l’attribut du Data Workbench est autre que [!UICONTROL mboxPC], vous devez modifier le paramètre de requête approprié et le renommer en _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Lorsque vous enregistrez le fichier d’exportation sur le serveur, l’exportation démarre. Une fois l’opération terminée, la variable [!UICONTROL TnTSend.exe] l’application se lance et commence à envoyer des données au compte Target.

## Configuration de Data Workbench pour Target

Effectuez les tâches suivantes dans Adobe Target :

Data Workbench transmet les profils utilisateur à Adobe Target. Pour effectuer la configuration en vue de l’exportation vers Target, vous devez configurer et activer son API et fournir la variable **[!UICONTROL clientname]** et **[!UICONTROL domain postfix]** paramètres du fichier de configuration d&#39;export (`export.cfg`).

Une nouvelle option booléenne appelée **[!UICONTROL Oneshot]** a été ajouté aux fichiers d’exportation de segments. Cette option est incluse dans le fichier de modèle distribué avec le nouveau profil. If [!UICONTROL Oneshot] est défini sur _true_, puis la variable `.export` sera renommé `.export.done-TIMESTAMP` une fois l’exportation terminée, en veillant à ce que le segment ne soit jamais exporté plus d’une fois. Ceci est important lors de l’exportation vers Adobe Target.

**Remarque :** Un appel d’un Data Workbench vers Adobe Target est comptabilisé comme une [!UICONTROL mbox] appel nécessitant un appel pour chaque profil envoyé. Par conséquent, les coûts augmentent si plusieurs appels sont nécessaires entre les deux solutions.

Une configuration incomplète génère le message d’erreur suivant dans le journal :

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configuration d’Adobe Target pour Data Workbench

Dans Adobe Target, aucune configuration spéciale n’est nécessaire pour qu’un client puisse envoyer des données de profil. Les informations de profil d’un utilisateur sont généralement transmises dans la variable [!UICONTROL mbox] et les serveurs rendront les paramètres de profil disponibles pour une configuration de campagne ciblée en tant que fonctionnalités standard sans configuration supplémentaire.

L’intégration de Data Workbench d’Adobe Target est intégrée. Elle peut être activée à partir de la page Détails du client super-utilisateur . L’activation de cette option fait apparaître les segments partagés à partir de Data Workbench dans Adobe Target afin de les rendre disponibles pour le ciblage.

## Définition des rapports de journal HTTP dans ExportIntegration.exe

Réduire les rapports longs à [!UICONTROL HTTP.log] lors de l’utilisation de [!UICONTROL ExportIntegration.exe] pour exporter des fichiers d’intégration Adobe Target.

Une nouvelle [!UICONTROL httpLoggingEI.cfg] fichier de configuration (situé à l’emplacement `server\Admin\Export\httpLoggingEI.cfg`) permet de réduire la journalisation en mode verbeux à la fonction [!UICONTROL HTTP.log] pour lors de l’exportation de données à l’aide de [!UICONTROL ExportIntegration.exe]. Cela vous permet d’arrêter la journalisation des requêtes/réponses en mode verbeux.

La journalisation en mode verbeux est déjà capturée dans [!UICONTROL TnTSend.log] fichiers .

_True_ définit la journalisation en mode verbeux et _False_ arrête la connexion en mode verbeux à [!UICONTROL HTTP.log] fichier .

Dans le paramètre False , seul un message d’avertissement est envoyé au [!UICONTROL HTTP.log] fichier (contenu d’information non envoyé).
