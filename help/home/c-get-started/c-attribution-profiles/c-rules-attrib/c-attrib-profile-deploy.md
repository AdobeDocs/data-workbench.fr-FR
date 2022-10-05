---
description: Le profil Attribution est un profil hérité prêt à l’emploi. En combinaison avec le profil SC Adobe et le flux de données Analytics (SC/Insight), le profil peut être déployé afin d’exposer rapidement les nouveaux modèles d’attribution sur les canaux numériques.
title: Déploiement du profil d’attribution
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# Déploiement du profil d’attribution{#deploying-the-attribution-profile}

{{eol}}

Le profil Attribution est un profil hérité prêt à l’emploi. En combinaison avec le profil SC Adobe et le flux de données Analytics (SC/Insight), le profil peut être déployé afin d’exposer rapidement les nouveaux modèles d’attribution sur les canaux numériques.

Après avoir enregistré le profil d’attribution sur le serveur Principal, deux étapes supplémentaires sont nécessaires pour l’intégrer au profil actuel dans le [!DNL Profile] directory: (1) Configurez le fichier Profile.cfg et (2) Déclarez les champs obligatoires.

## Configuration du fichier Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Comme tous les profils, le profil d’attribution doit être ajouté à la variable [!DNL profile.cfg] fichier . Comme le profil Attribution dépend du profil SC Adobe, le profil SC Adobe doit être répertorié en premier dans le fichier de configuration avant le profil Attribution.

>[!NOTE]
>
>Ces étapes nécessiteront une retransformation du jeu de données.

1. Ouvrez le [!DNL profile.cfg] dans votre dossier de profil personnalisé. (Ouvrir dans [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Si le profil d’attribution n’est pas répertorié dans le fichier de configuration, ajoutez-le à la liste. ![](assets/new_profile_cfg.png)

1. Assurez-vous que la variable **[!UICONTROL Attribution]** est répertoriée sous la chaîne **[!UICONTROL Adobe SC]** chaîne de profil.

1. Enregistrer la mise à jour [!DNL profile.cfg] puis enregistrez-le sur le serveur à partir du Gestionnaire de profils.

## Déclaration des champs obligatoires {#section-23d4273af0c34b7a85ae3430e2c9350e}

Le profil d’attribution utilise des champs prédéfinis et, avec une série de transformations, expose ces champs de manière nouvelle et utile par le biais de dimensions étendues. Pour fournir la valeur la plus immédiate, le profil d’attribution dépend des champs disponibles avec le profil SC d’Adobe.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variables par défaut </th> 
   <th colname="col2" class="entry"> Nom du champ et position du décodeur (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campagne </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canaux marketing </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événement de commande </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chiffre dʼaffaires </td> 
   <td colname="col2"> x-revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unités </td> 
   <td colname="col2"> <p>x-unités, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Vérifiez que ces champs sont déclarés dans le groupe de décodeur utilisé pour définir la source de données Adobe Analytics. Le groupe de décodeur par défaut est fourni sous [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Vérifiez que ces champs sont déclarés dans la variable **[!UICONTROL Fields]** de la section [!DNL SC Fields.cfg] fichier . Ce fichier peut se trouver sous [!DNL Dataset\Log Processing\SC Fields.cfg].

## Ajouts d’attribution et dépannage {#section-168133a8a1a54e1281e532033878d246}

Le profil Attribution a ajouté un fichier de configuration, [!DNL 0a_Marketing Channels.cfg], qui copie la valeur de la propriété [!DNL x-va_closer_detail] dans un nouveau champ appelé [!DNL x-marketing-channel], lorsque la variable [!DNL x-va_instance_event] correspond à &quot;1&quot;. Les [!DNL x-va_closer_detail] et [!DNL x-va_instant_event] sont décodés par défaut et transmis à partir du décodage dans les modules installés disponibles lors de la mise à jour vers la version 6.2.

Le [!DNL x-marketing-channel] est ensuite utilisé dans la dimension Simple appelée Canal marketing.

>[!IMPORTANT]
>
>Si vous avez modifié vos profils en supprimant les champs précédemment inutilisés qui sont maintenant utilisés, vous devez vérifier que la variable [!DNL x-va_closer_detail] et [!DNL x-va_instance_event] sont décodés et transmis pour utilisation.

Si des champs sont manquants, vous obtiendrez un message dans votre état détaillé :

```
<b>x-va_closer_detail</b> is not available
```

ou

```
<b>x-va_instance_event</b> is not available
```
