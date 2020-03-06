---
description: Ce document explique comment modifier toutes les configurations des outils de données par défaut une fois le nouveau schéma en place.
title: Modifications de configuration pour le nouveau schéma
uuid: 7d59fc28-ce56-49e2-b068-d5e286dcc057
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifications de configuration pour le nouveau schéma{#configuration-changes-for-new-schema}

Ce document explique comment modifier toutes les configurations des outils de données par défaut une fois le nouveau schéma en place.

## Présentation du schéma de jeu de données {#section-2ffac5170c894781bc943565af7ad479}

Le schéma du jeu de données repose sur un ensemble clé de relations qui forment la colonne vertébrale du schéma d’analyse Web des outils de données. Dans l’exemple suivant, un schéma analytique Web classique fournit une idée des relations entre un visiteur, une visite et une page vue. ![](assets/dwb_impl_schema_change1.png)

* Tout visiteur donné peut avoir une ou plusieurs visites.
* Une visite donnée est générée par un seul visiteur.
* Une visite donnée peut inclure une ou plusieurs pages vues.
* Une page vue donnée appartient à une seule visite. `<discoiqbr>`

Avec l&#39;évolution du Web et du monde des affaires, les besoins de l&#39;analyse des données et du Web ont également changé. Les sites Web ont commencé par être des endroits où regarder le contenu. Maintenant, vous pouvez regarder le contenu ; correspondre de manière interactive par le biais de conversations, de vidéos ou d&#39;envois ; les produits d&#39;achat; et bien plus encore. En outre, les entreprises veulent maintenant intégrer leurs données Web à d&#39;autres canaux de données dans leur entreprise afin de mieux comprendre leur activité dans son ensemble. Par exemple, une entreprise peut souhaiter intégrer ses données Web, de centre d’appels, de messagerie électronique, de réseau social et de stockage et de client ensemble. Avec cette intégration de canaux hors ligne et en ligne, les schémas des jeux de données ont évolué au fil des ans, où aucun schéma de jeux de données n&#39;est identique.

`<discoiqbr>`Lorsque vous intégrez les données en ligne et hors ligne, le terme &quot;visiteur&quot; ne semble pas toujours approprié. Par conséquent, le terme &quot;client&quot; est parfois utilisé à la place du visiteur. ![](assets/dwb_impl_schema_change2.png) ![](assets/dwb_impl_schema_change3.png)

Le niveau &quot;Engagement&quot; est utilisé pour activer une vue unique du temps, lorsque vous disposez de données provenant de plusieurs sources de données. Supposons, par exemple, que vous n’ayez qu’une seule source de données : Données de commerce électronique collectées par l’activité des visiteurs sur votre site Web. Dans ce cas, le niveau Visite indique les visites de ces visiteurs sur votre site. Notez que les dimensions temporelles - Jour, Semaine, Mois, etc. - sont généralement capturées au niveau &quot;Visite&quot;.

De même, le niveau &quot;Evénement&quot; renvoie tous les événements (page vue, appel effectué au centre d’appels, etc.) qui se sont produits au cours d’un engagement. Il combine tous les événements en ligne et hors ligne pour un client pendant un engagement.

## Nouvelle structure dénombrable dans DWB {#section-b77638ec04e4441cb51c56fd3d4abeb6}

La nouvelle structure de schéma remplace Visiteur par client, Visite par engagement et Accès par événement. ![](assets/dwb_impl_schema_change4.png)

## Modifications de la configuration conformément au nouveau schéma de jeu de données {#section-27135515be5c471ba2ee879d1ef4771f}

Pour modifier le schéma du jeu de données du visiteur au client, vous devez modifier les fichiers de configuration suivants :

1. Tous les fichiers de configuration sous le dossier Dataset où les dimensions dénombrables et étendues sont définies. ![](assets/dwb_impl_schema_change5.png)

1. Fichiers de configuration sous le dossier Dimension, où &quot;visiteur&quot;, &quot;visite&quot; ou &quot;événement&quot; sont utilisés comme niveau.

   Exemple : Fichier Campaign.cfg. Dans le profil Adobe SC, la campagne est définie au niveau de la visite. ![](assets/dwb_impl_schema_change6.png)

   L’exemple suivant donne une idée du changement de schéma parent de Visite à Engagement : ![](assets/dwb_impl_API10.png)

1. Certaines mesures étant dérivées ou créées à partir de tableaux, les fichiers de configuration situés sous le dossier Mesures doivent être modifiés ou créés.

   Par exemple : créez une mesure [!DNL Customers.metric with formula = sum(one,customer)] ou en tant que mesure Pages vues.metric pour la *définir* au niveau de l’accès. Modifiez la mesure, puis définissez le niveau sur Evénement au lieu d’Accès.

   Mesure Pages vues d’Adobe SC définie au niveau Accès : ![](assets/dwb_impl_API8.png)

   `<discoiqbr>` `<discoiqbr>`La mesure Pages vues sera la suivante, conformément au nouveau schéma : ![](assets/dwb_impl_API9.png)

1. Modifiez *order.txt* dans le dossier metrics afin qu’il reflète les nouvelles mesures ou les mesures modifiées liées au client, à l’engagement et à l’événement.

   Fichier Adobe *SC order.txt* . ![](assets/dwb_impl_API11.png)

   *Fichier Order.txt* avec modifications de schéma : ![](assets/dwb_impl_API12.png)

1. Tous les fichiers de configuration (.vw) sous le dossier Visualization doivent être modifiés pour faire référence aux nouveaux niveaux : Client, Engagement et Événement. Par exemple : Carte des processus 2D, Carte des processus 3D, etc.

   Le fichier URI.vw par défaut d’Adobe SC pour le mappage de processus 2D est défini au niveau Accès et Groupe de visites, comme illustré ci-dessous : ![](assets/dwb_impl_API14.png)

   Modifications à effectuer dans URI.vw pour le nouveau schéma : ![](assets/dwb_impl_API15.png)

