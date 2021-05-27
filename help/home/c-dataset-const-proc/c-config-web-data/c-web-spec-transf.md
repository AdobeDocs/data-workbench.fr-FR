---
description: Informations sur les paramètres spécifiques au web définis dans les fichiers d’inclusion de jeux de données de transformation distribués avec des profils d’Adobe pour le site.
title: Paramètres spécifiques web pour la transformation
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# Paramètres spécifiques web pour la transformation{#web-specific-settings-for-transformation}

Informations sur les paramètres spécifiques au web définis dans les fichiers d’inclusion de jeux de données de transformation distribués avec des profils d’Adobe pour le site.

Les conditions, dimensions et paramètres définis par ces paramètres sont créés lors de la phase de transformation de la construction du jeu de données.

* [Condition de page vue](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimension URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimension du référent](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Paramètres de session](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condition de page vue {#section-cc2807a12a88492f8b64a43234a1f835}

[!DNL Page View Condition] est une opération de condition qui détermine si une entrée de journal spécifique (c’est-à-dire une requête de page) doit être incluse dans les données collectées sur l’historique des pages vues d’un visiteur. Lorsque l’entrée de journal correspond à la valeur [!DNL Page View Condition], elle devient un élément de la dimension dénombrable Page vue. Si une entrée de journal ne correspond pas à [!DNL Page View Condition], ses champs de données sont toujours accessibles par d’autres dimensions. Outre la dimension Page vue , les dimensions suivantes peuvent être affectées par les résultats de la balise [!DNL Page View Condition] :

* **[!DNL URI]et  [!DNL Page] :** ces dimensions sont directement affectées par le  [!DNL Page View Condition]. Si la page donnée ne transmet pas la balise [!DNL Page View Condition,], elle n’est pas incluse dans les dimensions URI ou Page.

* **[!DNL Visitor Page Views]et  [!DNL Session Page Views] :** les dimensions Pages vues du visiteur et Pages vues de session sont un comptage du nombre de pages vues par un visiteur, respectivement, sur ou au cours d’une session donnée. Les pages filtrées par [!DNL Page View Condition] ne font pas partie de ce nombre.

* **Numéro de session :**  [!DNL Page View Condition] a un effet indirect sur la dimension Numéro de session. La dimension Numéro de session est créée avant [!DNL Page View Condition] ; par conséquent, lorsque vous considérez [!DNL Session Number] par rapport à [!DNL Page Views], il est possible d’avoir des sessions sans pages vues.

Votre mise en oeuvre par défaut de [!DNL Site] comprend un fichier [!DNL Transformation Dataset Include] dans lequel la dimension dénombrable Page vue et la [!DNL Page View Condition] associée sont définies.

Pour plus d’informations sur les dimensions dénombrables, voir [Dimensions étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Modification des paramètres de configuration de la condition Page vue**

1. Ouvrez le [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le fichier [!DNL Dataset\Transformation\Traffic\Page View.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres de [!DNL Page View Condition] selon les besoins. Utilisez l’exemple suivant comme guide. Dans ce fichier, [!DNL Page View Condition] est défini par une transformation [!DNL Copy]. Notez que ce fichier contient également la définition de la dimension dénombrable Page vue .

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Pour plus d’informations sur les dimensions dénombrables, voir [Dimensions étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Pour plus d’informations sur la transformation [!DNL Copy], voir [Transformations de données](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

## Dimension URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Si vous utilisez [!DNL Site], vous devez définir la dimension URI dont les éléments sont les racines URI des pages de site web consultées. Votre mise en oeuvre par défaut comprend un fichier [!DNL Transformation Dataset Include] dans lequel la dimension simple URI est définie.

Pour plus d’informations sur les dimensions simples, voir [Dimensions étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Pour modifier les paramètres de configuration de la dimension URI**

1. Ouvrez le [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le fichier [!DNL Dataset\Transformation\Traffic\URI.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres du fichier selon vos besoins. Utilisez l’exemple et les informations suivants comme guides.

![](assets/cfg_WebParameters_URI.png)

Les paramètres de configuration de la dimension URI incluent les deux paramètres suivants :

* **Respect de la casse :** True ou false. Si la valeur est true, la casse de la lettre (supérieure/inférieure) est prise en compte lors de l’identification des pages uniques. La valeur par défaut est true.
* **Maximum Elements** : nombre maximal d’éléments (c’est-à-dire, URI) pour la dimension URI. La valeur par défaut est 32768.

   >[!NOTE]
   >
   >La modification de cette valeur peut entraîner de graves problèmes de performances. Ne modifiez pas cette valeur sans Adobe de conseil.

* Enregistrez le fichier [!DNL URI.cfg] en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

* Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

## Dimension de référent {#section-8a97ec34d18b4814b5f95495ac4f8638}

Si vous utilisez [!DNL Site], vous devez définir la dimension Référent dont les éléments se composent des domaines de deuxième niveau des référents des premières entrées de journal dans toutes les sessions. Votre mise en oeuvre par défaut comprend un fichier [!DNL Transformation Dataset Include] dans lequel la dimension simple Référent est définie.

Pour plus d’informations sur les dimensions simples, voir [Dimensions étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Pour modifier les paramètres de configuration de la dimension Référent**

1. Ouvrez le [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le fichier [!DNL Dataset\Transformation\Traffic\Referrer.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres du fichier selon vos besoins. Utilisez l’exemple et les informations suivants comme guides.

   ![](assets/cfg_WebParameters_Referrer.png)

   Les paramètres de configuration de la dimension Référent incluent le paramètre Maximum Elements , qui spécifie le nombre maximal d’éléments (c’est-à-dire les référents) pour la dimension Référent . La valeur par défaut est 32768.

   >[!NOTE]
   >
   >Dans l’exemple ci-dessus, le paramètre [!DNL Maximum Elements] est défini sur 0. Lorsque ce paramètre est défini sur 0, le serveur Data Workbench utilise sa valeur par défaut interne 32768.

1. Enregistrez le fichier [!DNL Referrer.cfg] en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

## Paramètres de session {#section-0a209b0c504041a5801f7f71a963c8b1}

Si vous utilisez [!DNL Site], vous pouvez spécifier des paramètres qui définissent les limites de la session d’un visiteur sur un site web. Ces paramètres ne sont valides que lorsqu’ils sont définis dans un fichier [!DNL Transformation Dataset Include] dans votre implémentation [!DNL Site].

Les paramètres suivants sont uniques dans la mesure où ils peuvent être membres du [!DNL Transformation Dataset Include] vecteur [!DNL Parameters] du fichier ou être répertoriés en tant que paramètres individuels dans le fichier [!DNL Transformation.cfg]. Un paramètre peut être défini exactement une fois. Par conséquent, ces paramètres sont définis dans le fichier [!DNL Transformation.cfg]ou dans le vecteur [!DNL Parameters] du fichier d’inclusion du jeu de données, et non dans les deux fichiers.
**Durée maximale de la session et délai d’expiration de la session**

Durée maximale de la session et délai d’expiration de la session sont des paramètres de chaîne qui définissent la durée de la session d’un visiteur. Ces paramètres fonctionnent avec le paramètre Domaines internes pour déterminer la durée de session.

Durée maximale de la session spécifie la durée de session la plus longue avant le démarrage d’une nouvelle session. Cela empêche les pages web dont le contenu automatique est actualisé de créer des sessions arbitrairement longues. Si le référent d’un clic est défini sur l’une des entrées du paramètre Domaines internes , ce délai d’expiration est utilisé pour définir la fin d’une session. Aucune session ne peut être plus longue que la durée maximale de session spécifiée, quel que soit le nombre de clics qu’elle contient. La valeur recommandée est de 48 heures.

Le délai d’expiration de la session spécifie le temps qui doit s’écouler entre les entrées de journal d’un visiteur donné pour déterminer la fin d’une session et le début d’une nouvelle session (c’est-à-dire le délai d’expiration type utilisé pour définir une session utilisateur). La valeur recommandée de ce paramètre est de 30 minutes. Si le référent d’un clic n’est pas défini sur l’un des référents dans le paramètre Domaines internes , ce délai d’expiration est utilisé pour définir la session. Si cs(referrer-domain) pour une entrée de journal se trouve dans la liste des domaines internes, la durée maximale de la session détermine si l’entrée de journal active fait partie d’une session existante ou si elle commence une nouvelle session.

Supposons qu’un visiteur soit appelé hors de son ordinateur pendant une période plus longue que le délai d’expiration de la session alors qu’il navigue sur le site. À son retour, il continue de naviguer là où il s&#39;est arrêté. Comme le visiteur ne quitte jamais le site ou ferme son navigateur, le cs(domaine-référent) de son prochain clic est identique au domaine interne. Sa session d’origine reste principale tant que le paramètre Durée maximale de la session n’est pas atteint. Si le domaine du site est répertorié comme domaine interne et que le délai d’expiration maximal n’est pas atteint, l’interaction du visiteur s’affiche sous la forme d’une session unique et non de deux sessions distinctes. Cependant, si le visiteur revient sur son ordinateur et que son clic suivant comporte un référent externe (ou vide), une nouvelle session commence.

>[!NOTE]
>
>[!DNL Sessionize] transformation [!DNL Timeout Condition] joue également un rôle pour déterminer la durée de la session d’un visiteur. Si le délai d’expiration de la session et la durée maximale de la session ne s’appliquent pas, la case [!DNL Timeout Condition] est cochée pour déterminer si une entrée de journal doit être considérée comme le début d’une nouvelle session. Pour plus d’informations, voir [Transformations de données](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Modification des paramètres Durée maximale de la session et Délai d’expiration de la session**

Si vous utilisez [!DNL Site], votre mise en oeuvre par défaut inclut probablement un fichier [!DNL Transformation Dataset Include] dans lequel les noms et les valeurs recommandées de ces paramètres sont spécifiés.

1. Ouvrez le [!DNL Profile Manager] dans votre profil de jeu de données et accédez à [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres sont définis peut différer de l’emplacement décrit.

1. Modifiez les valeurs des paramètres selon vos besoins. Veillez à spécifier les unités souhaitées (minutes, heures, etc.).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Enregistrez le fichier [!DNL Session Parameters.cfg] en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis en cliquant sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, où le nom du profil est le nom du profil du jeu de données ou du profil hérité auquel appartient le fichier d’inclusion du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

**[!DNL Internal Domains]**

[!DNL Internal Domains] est un paramètre vectoriel qui répertorie les hôtes au niveau du domaine (référents internes) qui doivent être traités comme faisant partie d’un site web particulier. Ces hôtes sont supprimés de la dimension de référent (qui est une liste des informations de référent externe). Lorsque cs(referrer-domain) correspond à l’une des chaînes répertoriées dans le jeu de domaines internes, le délai d’expiration de la session est ignoré et la durée maximale de la session est utilisée pour déterminer la durée de la session.

Le paramètre Domaines internes peut également être utilisé pour empêcher le début d’une nouvelle session lorsque les visiteurs passent d’un domaine à l’autre d’une société, d’une manière qui dépasse le délai d’expiration de la session. Prenons l’exemple d’une société dont des parties de son site sont réparties sur deux domaines : l’un est consigné ( [!DNL xyz.com]), l’autre n’est pas consigné ( [!DNL xyz-unlogged.com]). Si ces sites sont intégrés de manière à faciliter le déplacement transparent du trafic entre les deux domaines, il n’est pas souhaitable de générer une session différente chaque fois que le visiteur passe du domaine [!DNL xyz-unlogged.com] au domaine [!DNL xyz.com]. L’énumération de [!DNL xyz-unlogged.com] en tant que domaine interne empêche le fractionnement des sessions en plusieurs sessions en raison du trafic sur ces deux domaines tant que le paramètre Durée maximale de la session n’est pas atteint.

**Pour ajouter un domaine interne**

Si vous utilisez [!DNL Site], votre mise en oeuvre par défaut comprend un fichier [!DNL Transformation Dataset Include] permettant de définir le paramètre Domaines internes. Dans ce fichier, le paramètre est nommé . il vous suffit de saisir les domaines internes que vous souhaitez inclure et d’enregistrer le fichier mis à jour.

1. Ouvrez le [!DNL Profile Manager] dans votre profil de jeu de données et accédez à [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel le paramètre Domaines internes est défini peut différer de l’emplacement décrit.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Value]** pour le paramètre vectoriel Domaines internes et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Modifiez les valeurs selon vos besoins.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Enregistrez le fichier [!DNL Internal Domains.cfg] en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis en cliquant sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL profile name]***, où le nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.
