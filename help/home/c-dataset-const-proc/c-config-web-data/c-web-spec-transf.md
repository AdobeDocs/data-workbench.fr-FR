---
description: Informations sur les paramètres spécifiques au Web définis dans le jeu de données de transformation Incluez les fichiers fournis avec les profils Adobe pour le site.
solution: Analytics
title: Paramètres spécifiques au Web pour la transformation
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Paramètres spécifiques au Web pour la transformation{#web-specific-settings-for-transformation}

Informations sur les paramètres spécifiques au Web définis dans le jeu de données de transformation Incluez les fichiers fournis avec les profils Adobe pour le site.

Les conditions, dimensions et paramètres définis par ces paramètres sont créés pendant la phase de transformation de la construction du jeu de données.

* [Condition Page vue](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimension URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimension Référent](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Paramètres de session](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condition Page vue {#section-cc2807a12a88492f8b64a43234a1f835}

Il [!DNL Page View Condition] s’agit d’une opération de condition qui détermine si une entrée de journal spécifique (c’est-à-dire une requête de page) doit être incluse dans les données rassemblées sur l’historique des pages vues d’un visiteur. Lorsque l’entrée de journal satisfait à la [!DNL Page View Condition], elle devient un élément de la dimension dénombrable Page vue. Si une entrée de journal ne satisfait pas [!DNL Page View Condition], ses champs de données sont toujours accessibles par d’autres dimensions. Outre la dimension Page vue, les dimensions suivantes peuvent être affectées par les résultats de la [!DNL Page View Condition]:

* **[!DNL URI]et[!DNL Page]:**Ces dimensions sont directement affectées par le[!DNL Page View Condition]. Si la page donnée ne transmet pas la page,[!DNL Page View Condition,]elle n’est pas incluse dans les dimensions URI ou Page.

* **[!DNL Visitor Page Views]et[!DNL Session Page Views]:**Les dimensions Pages vues du visiteur et Pages vues de la session représentent le nombre de pages vues par un visiteur au cours d’une session donnée, respectivement. Les pages filtrées par le[!DNL Page View Condition]ne font pas partie de ce décompte.

* **Numéro de session :** Cela [!DNL Page View Condition] a un effet indirect sur la dimension Numéro de session. La dimension Numéro de session est créée avant la [!DNL Page View Condition]; par conséquent, lorsqu’on examine [!DNL Session Number] la question par rapport au [!DNL Page Views], il est possible d’avoir des sessions sans pages vues.

Votre implémentation par défaut de [!DNL Site] inclut un [!DNL Transformation Dataset Include] fichier dans lequel la dimension dénombrable Page vue et les éléments associés [!DNL Page View Condition] sont définis.

Pour plus d’informations sur les dimensions dénombrables, voir Dimensions [étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Pour modifier les paramètres de configuration de la condition Page vue**

1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le [!DNL Dataset\Transformation\Traffic\Page View.cfg] fichier.

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres de la [!DNL Page View Condition] variable selon vos besoins. Utilisez l’exemple suivant comme guide. Dans ce fichier, la [!DNL Page View Condition] valeur est définie par une [!DNL Copy] transformation. Notez que ce fichier contient également la définition de la dimension dénombrable Page vue.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Pour plus d’informations sur les dimensions dénombrables, voir Dimensions [étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Pour plus d’informations sur la [!DNL Copy] transformation, voir Transformations des [données](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

## Dimension URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Si vous travaillez avec [!DNL Site], vous devez définir la dimension URI dont les éléments sont les racines URI des pages de site Web affichées. Votre implémentation par défaut comprend un [!DNL Transformation Dataset Include] fichier dans lequel la dimension simple URI est définie.

Pour plus d’informations sur les dimensions simples, voir Dimensions [étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Pour modifier les paramètres de configuration de la dimension URI**

1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le [!DNL Dataset\Transformation\Traffic\URI.cfg] fichier.

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres du fichier selon vos besoins. Utilisez l’exemple et les informations suivants comme guides.

![](assets/cfg_WebParameters_URI.png)

Les paramètres de configuration de la dimension URI incluent les deux paramètres suivants :

* **Respect de la casse :** True ou false. Si la valeur est true, la casse de la lettre (majuscule/minuscule) est prise en compte lors de l’identification des pages uniques. La valeur par défaut est true.
* **Eléments max. :** Nombre maximal d’éléments (URI) pour la dimension URI. La valeur par défaut est 32768.

   >[!NOTE]
   >
   >La modification de cette valeur peut entraîner de sérieux problèmes de performances. Ne modifiez pas cette valeur sans consulter Adobe.

* Enregistrez le [!DNL URI.cfg] fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez **[!UICONTROL Save]**.

* Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

## Dimension Référent {#section-8a97ec34d18b4814b5f95495ac4f8638}

Si vous travaillez avec [!DNL Site], vous devez définir la dimension Référent dont les éléments sont constitués des domaines de deuxième niveau des référents des premières entrées de journal dans toutes les sessions. Votre implémentation par défaut comprend un [!DNL Transformation Dataset Include] fichier dans lequel la dimension simple Référent est définie.

Pour plus d’informations sur les dimensions simples, voir Dimensions [étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Pour modifier les paramètres de configuration de la dimension Référent**

1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données et ouvrez le [!DNL Dataset\Transformation\Traffic\Referrer.cfg] fichier.

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres de configuration existent peut différer de l’emplacement décrit.

1. Vérifiez ou modifiez les valeurs des paramètres du fichier selon vos besoins. Utilisez l’exemple et les informations suivants comme guides.

   ![](assets/cfg_WebParameters_Referrer.png)

   Les paramètres de configuration de la dimension Référent incluent le paramètre Eléments maximaux, qui spécifie le nombre maximal d’éléments (c’est-à-dire de référents) pour la dimension Référent. La valeur par défaut est 32768.

   >[!NOTE]
   >
   >Dans l’exemple ci-dessus, le [!DNL Maximum Elements] paramètre est défini sur 0. Lorsque ce paramètre est défini sur 0, le serveur de l’outil de données utilise sa valeur par défaut interne, 32768.

1. Enregistrez le [!DNL Referrer.cfg] fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

## Paramètres de session {#section-0a209b0c504041a5801f7f71a963c8b1}

Si vous travaillez avec [!DNL Site], vous pouvez spécifier des paramètres qui définissent les limites de la session d’un visiteur sur un site Web. Ces paramètres ne sont valides que lorsqu’ils sont définis dans un [!DNL Transformation Dataset Include] fichier au sein de votre [!DNL Site] implémentation.

Les paramètres suivants sont uniques en ce sens qu’ils peuvent être membres du [!DNL Transformation Dataset Include] vecteur du fichier ou être répertoriés comme des paramètres individuels dans le [!DNL Parameters] [!DNL Transformation.cfg]fichier. Un paramètre peut être défini exactement une fois. Ces paramètres sont donc définis dans le [!DNL Transformation.cfg]fichier ou dans le [!DNL Parameters] vecteur du fichier d’inclusion du jeu de données, et non dans les deux fichiers.
**Durée maximale de session et expiration de session**

Durée maximale de session et Délai d’expiration de session sont des paramètres de chaîne qui définissent la durée de la session d’un visiteur. Ces paramètres fonctionnent avec le paramètre Domaines internes pour déterminer la durée de session.

Durée maximale de la session indique la durée de session la plus longue avant le démarrage d’une nouvelle session. Cela évite aux pages Web dont le contenu automatique est actualisé de créer des sessions arbitrairement longues. Si le référent d’un clic est défini sur l’une des entrées du paramètre Domaines internes, ce délai d’expiration est utilisé pour définir la fin d’une session. Aucune session ne peut être plus longue que la durée maximale de session spécifiée, quel que soit le nombre de clics qu’elle contient. La valeur recommandée est de 48 heures.

Le délai d’expiration de la session indique le délai qui doit s’écouler entre les entrées du journal d’un visiteur donné pour déterminer la fin d’une session et le début d’une nouvelle session (c’est-à-dire le délai d’expiration habituel utilisé pour définir une session utilisateur). La valeur recommandée pour ce paramètre est de 30 minutes. Si le référent d’un clic n’est pas défini sur l’un des référents du paramètre Domaines internes, ce délai d’expiration est utilisé pour définir la session. Si cs(referrer-domain) pour une entrée de journal se trouve dans la liste des domaines internes, la durée maximale de la session détermine si l&#39;entrée de journal active fait partie d&#39;une session existante ou du début d&#39;une nouvelle session.

Imaginons qu’un visiteur soit appelé hors de son ordinateur pendant une période plus longue que le délai d’expiration de la session alors qu’il navigue sur le site. À son retour, il continue à naviguer là où il s&#39;est arrêté. Comme le visiteur ne quitte jamais le site ou ne ferme jamais son navigateur, le cs(domaine-référent) de son prochain clic est identique au domaine interne et sa session d’origine reste active tant que le paramètre Durée maximale de la session n’est pas atteint. Si le domaine du site est répertorié comme domaine interne et que le délai d’expiration maximal n’est pas atteint, l’interaction du visiteur s’affiche sous la forme d’une seule session et non de deux sessions distinctes. Cependant, si le visiteur revient sur son ordinateur et que son clic suivant comporte un référent externe (ou vide), une nouvelle session commence.

>[!NOTE]
>
>La [!DNL Sessionize] transformation [!DNL Timeout Condition] joue également un rôle dans la détermination de la durée de la session d’un visiteur. Si le délai d’expiration de la session et la durée maximale de la session ne s’appliquent pas, le [!DNL Timeout Condition] système vérifie si une entrée de journal doit être considérée comme le début d’une nouvelle session. For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Pour modifier les paramètres Durée maximale de session et Délai d’expiration de session**

Si vous travaillez avec [!DNL Site], votre implémentation par défaut comprend probablement un [!DNL Transformation Dataset Include] fichier dans lequel les noms et les valeurs recommandées de ces paramètres sont spécifiés.

1. Ouvrez le fichier [!DNL Profile Manager] dans votre profil de jeu de données et accédez à [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel ces paramètres sont définis peut différer de l’emplacement décrit.

1. Modifiez les valeurs des paramètres selon vos besoins. Veillez à spécifier les unités souhaitées (minutes, heures, etc.).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Enregistrez le [!DNL Session Parameters.cfg] fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d’inclusion du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

**[!DNL Internal Domains]**

[!DNL Internal Domains] est un paramètre vectoriel qui répertorie les hôtes au niveau du domaine (référents internes) qui doivent être traités comme faisant partie d’un site Web particulier. Ces hôtes sont supprimés de la dimension de référent (liste des informations de référent externe). Lorsque cs(referrer-domain) correspond à l’une des chaînes répertoriées dans le jeu de domaines internes, le délai d’expiration de la session est ignoré et la durée maximale de la session est utilisée pour déterminer la durée de la session.

Le paramètre Domaines internes peut également être utilisé pour empêcher le début d’une nouvelle session lorsque les visiteurs se déplacent parmi les plusieurs domaines d’une entreprise associés d’une manière qui dépasse le délai d’expiration de la session. Prenons l’exemple d’une entreprise dont certaines parties de son site sont réparties sur deux domaines : l’une est enregistrée ( [!DNL xyz.com]), l’autre n’est pas enregistrée ( [!DNL xyz-unlogged.com]). Si ces sites sont intégrés d’une manière qui facilite le déplacement transparent du trafic entre les deux domaines, il n’est pas souhaitable de générer une session différente chaque fois que le visiteur revient d’un [!DNL xyz-unlogged.com] domaine au [!DNL xyz.com] domaine. La liste [!DNL xyz-unlogged.com] sous forme de domaine interne empêche la division des sessions en plusieurs sessions en raison du trafic sur ces deux domaines tant que le paramètre Durée maximale de la session n’est pas atteint.

**Pour ajouter un domaine interne**

Si vous travaillez avec [!DNL Site], votre implémentation par défaut comprend un [!DNL Transformation Dataset Include] fichier pour la définition du paramètre Domaines internes. Dans ce fichier, le paramètre est nommé ; il vous suffit de saisir les domaines internes que vous souhaitez inclure et d’enregistrer le fichier mis à jour.

1. Ouvrez le [!DNL Profile Manager] profil du jeu de données et accédez à [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Si vous avez personnalisé votre implémentation de [!DNL Site], le fichier dans lequel le paramètre Domaines internes est défini peut différer de l’emplacement décrit.

1. Cliquez avec le bouton droit **[!UICONTROL Value]** pour le paramètre vectoriel Domaines internes et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Modifiez les valeurs selon vos besoins.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Enregistrez le [!DNL Internal Domains.cfg] fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant **[!UICONTROL Save]**.

1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;>**[!UICONTROL profile name]***, où nom du profil correspond au nom du profil du jeu de données ou au profil hérité auquel appartient le fichier d&#39;inclusion du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

