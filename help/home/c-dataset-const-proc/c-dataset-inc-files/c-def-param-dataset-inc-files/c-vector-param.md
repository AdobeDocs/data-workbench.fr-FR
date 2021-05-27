---
description: Les paramètres vectoriels contiennent plusieurs valeurs pour une seule variable.
title: Paramètres vectoriels
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
exl-id: c6140bdf-dcd9-4fa9-a6e0-34cbc45414d0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%

---

# Paramètres vectoriels{#vector-parameters}

Les paramètres vectoriels contiennent plusieurs valeurs pour une seule variable.

Vous ne pouvez référencer les paramètres vectoriels que comme seul élément d’un vecteur. Cet exemple illustre un fichier [!DNL Transformation Dataset Include] qui définit un paramètre vectoriel. Le paramètre vectoriel &quot;Domaines internes&quot; se compose de trois valeurs.

![](assets/cfg_WebParameters_InternalDomains.png)

Notez que le paramètre vectoriel est le seul élément répertorié pour le vecteur [!DNL Matches] dans la condition [!DNL String Match].

![](assets/cfg_Parameters_InternalDomains_Ref.png)

Pour plus d’informations sur les domaines internes, voir [Paramètres de configuration pour les données web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519). Pour plus d’informations sur la condition [!DNL String Match], voir [Conditions](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
