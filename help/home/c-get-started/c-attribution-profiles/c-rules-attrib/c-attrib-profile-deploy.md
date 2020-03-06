---
description: Le profil Attribution est un profil hérité prêt à l’emploi. Associé au profil Adobe SC et au flux de données Analytics (SC/Insight), le profil peut être déployé pour exposer rapidement de nouveaux modèles d’attribution sur les canaux numériques.
title: Déploiement du profil d’attribution
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Déploiement du profil d’attribution{#deploying-the-attribution-profile}

Le profil Attribution est un profil hérité prêt à l’emploi. Associé au profil Adobe SC et au flux de données Analytics (SC/Insight), le profil peut être déployé pour exposer rapidement de nouveaux modèles d’attribution sur les canaux numériques.

Après avoir enregistré le profil d’attribution sur le serveur principal, deux étapes supplémentaires sont nécessaires pour l’intégrer au profil actuel dans le [!DNL Profile] répertoire : (1) Configurez le fichier Profile.cfg et (2) Déclarez les champs obligatoires.

## Configuration du fichier Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Comme tous les profils, le profil d’attribution doit être ajouté au [!DNL profile.cfg] fichier. Le profil d’attribution dépendant du profil Adobe SC, le profil Adobe SC doit être répertorié en premier dans le fichier de configuration avant le profil d’attribution.

>[!NOTE]
>
>Ces étapes nécessiteront une retransformation du jeu de données.

1. Ouvrez le [!DNL profile.cfg] fichier dans votre dossier de profil personnalisé. (Ouvrir dans [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Si le profil d’attribution n’est pas répertorié dans le fichier de configuration, ajoutez-le à la liste. ![](assets/new_profile_cfg.png)

1. Assurez-vous que la **[!UICONTROL Attribution]** chaîne est répertoriée sous la chaîne **[!UICONTROL Adobe SC]** de profil.

1. Enregistrez le [!DNL profile.cfg] fichier mis à jour, puis enregistrez-le sur le serveur à partir du Gestionnaire de profils.

## Déclaration des champs obligatoires {#section-23d4273af0c34b7a85ae3430e2c9350e}

Le profil d’attribution utilise des champs prédéfinis et, avec une série de transformations, expose ces champs de manière nouvelle et utile à travers des dimensions étendues. Pour fournir la valeur la plus immédiate possible, le profil d’attribution dépend des champs disponibles avec le profil Adobe SC.

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
   <td colname="col1"> Evénement de commande </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recettes </td> 
   <td colname="col2"> x-revenu, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unités </td> 
   <td colname="col2"> <p>x-units, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Vérifiez que ces champs sont déclarés dans le groupe de décodeurs utilisé pour définir la source de données Adobe Analytics. Le groupe de décodeurs par défaut est fourni sous [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Vérifiez que ces champs sont déclarés dans la **[!UICONTROL Fields]** section du [!DNL SC Fields.cfg] fichier. Ce fichier peut être situé sous [!DNL Dataset\Log Processing\SC Fields.cfg].

## Ajouts d’attribution et dépannage {#section-168133a8a1a54e1281e532033878d246}

Le profil d’attribution a ajouté un fichier de configuration [!DNL 0a_Marketing Channels.cfg], qui copie la valeur de la [!DNL x-va_closer_detail] balise dans un nouveau champ appelé [!DNL x-marketing-channel], lorsque le [!DNL x-va_instance_event] champ correspond à &quot;1&quot;. Les deux [!DNL x-va_closer_detail] et [!DNL x-va_instant_event] sont décodés par défaut et transmis à partir du décodage dans les paquets installés disponibles lors de la mise à jour vers la version 6.2.

Le [!DNL x-marketing-channel] champ est ensuite utilisé dans la dimension Simple appelée Canal marketing.

>[!IMPORTANT]
>
>Si vous avez modifié vos profils en supprimant les champs précédemment inutilisés qui sont maintenant utilisés, vous souhaiterez vérifier que les champs [!DNL x-va_closer_detail] et [!DNL x-va_instance_event] sont décodés et transmis pour utilisation.

Si des champs sont manquants, vous recevrez un message dans votre état détaillé :

```
<b>x-va_closer_detail</b> is not available
```

ou

```
<b>x-va_instance_event</b> is not available
```

