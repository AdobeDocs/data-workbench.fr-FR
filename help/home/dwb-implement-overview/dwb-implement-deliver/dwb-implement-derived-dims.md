---
description: Les différents types de Dimensions dérivées (côté client) et comment les configurer dans Data Workbench.
title: Configuration des dimensions dérivées
uuid: 9d2416fb-1c29-45a8-91d0-ddca575224ad
exl-id: 79c72135-e527-4755-b43f-eacc63d765aa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2100'
ht-degree: 0%

---

# Configuration des dimensions dérivées{#derived-dimensions-setup}

{{eol}}

Les différents types de Dimensions dérivées (côté client) et comment les configurer dans Data Workbench.

## Types de Dimensions dérivées {#section-33e6dcc9ab9745de9b830cecb2427ca3}

**Dimensions de mesure**

La Dimension de mesures vous permet de regrouper les mesures selon un niveau spécifique. Il vous permet également de regrouper les mesures selon un niveau spécifique. Une fois qu’une Dimension de mesure est créée, vous pouvez segmenter les données en fonction de la valeur de mesure.

Exemple 1 : Vous êtes une agence de voyages et vous voulez comprendre la différence entre les activités comportementales de votre site web entre vos voyageurs fréquents et les clients qui ont réservé un vol moins de 5 fois ? Comment feriez-vous cela ?

Tout ce que vous avez, c’est le décompte des réservations en tant que mesure. Comment segmenterez-vous les clients en fonction d’une mesure (ici, réservation) pour comprendre leur comportement sur le site web ?

Exemple 2 : Vous êtes une banque financière et vous souhaitez regrouper vos clients en fonction du nombre de CD dans lesquels ils ont investi. Vous souhaitez segmenter vos clients en 3 niveaux. Niveau 1 - Clients avec plus de 10 CD, niveau 2 - Clients avec plus de 5 et &lt;10 CD et niveau 3 - Clients avec plus de 0 et &lt;5 CD

Les informations dont vous disposez sont des mesures qui vous donnent un décompte des investissements dans les CD. Comment allez-vous créer des segments clients fatigués pour votre analyse ?

*Création d’une Dimension de mesure - via Workstation*

Marquez l’une des dimensions de mesure OOB comme locale et Renommez cette dimension avec un nom personnalisé / Effectuez une copie locale de l’exemple RenameDim.et renommez-la en nom de dimension approprié avec l’extension .dim .

Ouvrez la nouvelle dimension dans le poste de travail pour apporter des modifications. Modifiez les paramètres suivants de la dimension de mesure en fonction des exigences : ![](assets/dwb_impl_derived_dims1.png)

Mesure : mesure à regrouper.

Niveau : niveau auquel les mesures seront regroupées.

Début du compartiment : élément de départ de la Dimension de mesure. Saisissez la même valeur dans le décalage.

Taille de l’intervalle : taille de l’ensemble de la mesure. Saisissez la même valeur dans l’échelle.

Nombre de compartiments : nombre maximal d’éléments à afficher dans la dimension.

Enregistrez la nouvelle dimension sur le serveur si vous souhaitez la partager avec d’autres personnes.

**Dimensions de préfixe**

L’objectif principal de la dimension Préfixe est de regrouper des éléments de la dimension d’origine et de fournir des noms conviviaux aux éléments regroupés.

Par exemple, vous possédez un site de vente au détail et votre site comporte différentes sections comme Vêtements pour femmes, Vêtements pour homme, Jouets et Jeux, Décoration d’accueil, etc. Chacune de ces sections de site comporte plusieurs pages qui lui sont associées. Vous souhaitez analyser les chemins et obtenir des informations sur le trafic qui va d’une section de site à une autre, etc. Si vous utilisez la dimension URI, vous devrez extraire chaque page de chaque section du site dans l’explorateur de chemins d’accès ou la cartographie des processus et poursuivre l’analyse.

La même analyse peut être effectuée facilement s’il existe une dimension Préfixe dont les pages d’une section de site sont regroupées en un seul élément.

Création d’une Dimension de préfixe :

Ouvrez une cartographie des processus 2D à partir du menu Visualisation .

Modifiez les paramètres suivants de la dimension de préfixe en fonction des exigences.

Modifier la Dimension de mappage : Dimension que vous souhaitez utiliser pour la carte de processus 2D (par exemple : Typologie des SMS)

Modifier la Dimension au niveau de la carte - Niveau de la dimension mentionnée ci-dessus

Modifier la Dimension du clip de carte : niveau dénombrable auquel vous souhaitez consulter les données.

Modifier la mesure de carte : mesure à examiner.

Une fois la carte du processus 2D définie, ouvrez la dimension que vous avez mentionnée dans le paramètre de Dimension de la carte des modifications .

Sélectionnez les éléments que vous souhaitez regrouper. Utilisez CTRL+ALT et faites glisser et déposez les éléments sur la cartographie des processus.

Cliquez avec le bouton droit sur le point qui s’affiche et renommez le groupe. Si vous avez sélectionné 3 éléments à regrouper, le nom par défaut sera 3 sélectionnés.

Cliquez avec le bouton droit sur le contour de la visualisation et enregistrez la dimension dans le menu qui s’affiche.

**Renommer les Dimensions**

Les Dimensions de changement de nom sont créées à partir d’une dimension préexistante. L’objectif principal de la dimension renommée est de fournir des noms conviviaux aux éléments de la dimension. La dimension Renommer prête à l’emploi est la dimension Page créée à partir de la dimension URI. La dimension URI peut être déroutante pour une personne qui ne connaît pas les noms techniques des pages. C’est pourquoi la dimension Page vous permet de renommer des éléments de la dimension URI.

CRÉATION DE DIMENSIONS DE RENOMMAGE PERSONNALISÉES :

Les éléments de la dimension Renommée contiennent un mappage Un-à-un avec les éléments de la dimension de base d’origine. Vous pouvez le vérifier en ouvrant le fichier .dim de la Dimension Renommer dans le bloc de notes/station de travail. Vous remarquerez que chaque élément de la dimension d’origine n’a qu’une seule valeur (Renommer la chaîne) par rapport à celui-ci dans le fichier.

Si vous avez moins d’éléments à renommer ; vous pouvez créer un fichier .dim dans le poste de travail et renommer chaque élément en suivant les étapes décrites ci-dessous.

Procédure de création d’un fichier .dim pour une Dimension Renommer - Utilisation de Workstation

Utilisez cette option si le nombre d’éléments à renommer est inférieur.

1. Ouvrez un espace de travail vierge et ouvrez le Gestionnaire de Dimensions. Cliquez avec le bouton droit de la souris > Admin > Profil > Gestionnaire de profils.
1. Développez le dossier Dimensions dans la colonne Fichier .
1. Développez le dossier Page dans la colonne Fichier et cliquez avec le bouton droit sur le fichier Page.dim dans la deuxième colonne à la dernière (cette colonne représente généralement le nom du profil), puis cliquez sur l’option &quot;Rendre local&quot;.
1. Cliquez avec le bouton droit de la souris sur Page.dim dans la colonne &quot;Utilisateur&quot;, cliquez sur l’option Copier et collez le fichier .dim copié dans le dossier de votre choix sous le répertoire Dimensions.
1. Cliquez sur OK dans le message d’erreur.
1. Vous remarquerez maintenant qu’il existe deux fichiers Page.dim sous le dossier Dimensions. L’un est le fichier d’origine sous le répertoire Dimensions\Page et l’autre est celui que vous copiez collé à l’étape 4.
1. Cliquez avec le bouton droit de la souris sur le fichier Page.dim récemment collé sous la colonne Utilisateur, puis cliquez sur la zone de saisie bleu/gris qui indique Page.dim. La zone de saisie devient verte et le curseur clignote, ce qui indique qu’elle peut être modifiée. Saisissez le nom de la dimension Renommer que vous souhaitez créer.
1. Vous remarquerez que le fichier Page.dim de la colonne Fichier a été remplacé par le nouveau nom de fichier que vous avez donné à l’étape 7. Cliquez avec le bouton droit sur le fichier new.dim dans la colonne Utilisateur (Dernière colonne) et sélectionnez Ouvrir > Dans Workstation.
1. Une fois le fichier .dim ouvert dans le poste de travail ; cliquez sur le signe plus (+) en regard de l’entité et développez-le. Observez la valeur présente par rapport au champ &quot;Parent&quot;, elle reflète la dimension &quot;URI&quot;. Il affiche &quot;wdata/model/dim/URI&quot; Cliquez sur la zone de saisie bleue/grise pour remplacer l’URI par le nom de la dimension dont vous souhaitez renommer les éléments.
1. Assurez-vous que la dimension que vous souhaitez renommer existe dans le jeu de données. Les noms des Dimensions sont sensibles à la casse. Conservez donc la casse de la dimension d’origine.
1. Observez la &quot;modification&quot; apparaissant en regard du nom de la dimension. Cela indique que la dimension d’origine a été modifiée. Soutenir les modifications apportées à l&#39;étape 9; Cliquez avec le bouton droit de la souris sur new.dim (modifié) et cliquez sur l’option &quot;Enregistrer sous&quot;.
1. Une fois la dimension enregistrée à l’étape 10, la nouvelle dimension Renommer des campagnes vous est désormais accessible dans le but de la renommer. Cette option n’est disponible que localement.
1. Pour que d’autres personnes puissent voir la dimension créée par vous, elle doit être enregistrée sur le profil. Cliquez avec le bouton droit sur le fichier .dim de la nouvelle dimension dans la colonne &quot;Utilisateur&quot; (Dernière colonne) et cliquez sur &quot;Enregistrer dans > Nom du profil&quot; dans lequel vous souhaitez enregistrer la dimension.
1. Après avoir enregistré le fichier dans le profil, tous les utilisateurs de la station de travail ayant accès à ce profil pourront voir la dimension renommée des campagnes.

Outil de préfixe et de changement de nom du créateur dynamique

Adobe dispose d’un outil Excel pour générer des Dimensions Préfixe et Renommer.

Vous trouverez ci-dessous les étapes de génération des dimensions Préfixe/Renommer à l’aide de l’outil :

1. Enregistrement de l’outil Excel *Adobe_DWB_Dimension_Generator.xlsm* dans un dossier. Contactez l’assistance clientèle d’Adobe pour télécharger l’outil.
1. Ouvrez l’outil et activez les macros : ![](assets/dwb_impl_derived_dims2.png)

1. Remplissez la feuille de données avec les valeurs à utiliser.

   Par exemple, nous créons la dimension Préfixe de marque de produit en fonction de la Dimension de produit. Dans la feuille de données, les informations suivantes sont capturées : ![](assets/dwb_impl_derived_dims3.png)

   Chaque produit est affecté à une marque dans la feuille de données.

1. Dans l&#39;onglet Configuration , renseignez les informations relatives à la dimension à créer. Pour les exemples de données ci-dessus, les informations sont renseignées : ![](assets/dwb_impl_derived_dims4.png)

   Nom : Nom de la dimension Préfixe/Renommer

   Type : Préfixe/Renommer

   Dim source : Dimension originale

   Correspondance avec la colonne : Colonne à mettre en correspondance

   Colonne de résultats : Valeur à utiliser pour la nouvelle dimension.

1. Cliquez sur le bouton intitulé *Cliquez ici*. ![](assets/dwb_impl_derived_dims5.png)

1. Le fichier dim sera généré dans le dossier où l’outil a été enregistré. ![](assets/dwb_impl_derived_dims6.png)

   À l’aide du Gestionnaire de profils, enregistrez le fichier dim dans le dossier Dimension.

**Maj de Dimensions**

Les dimensions avec décalage vous permettent de consulter l’élément énième d’une dimension au niveau de n’importe quelle Dimension dénombrable spécifique.

Elles vous permettent également de regarder en arrière le N° élément de n’importe quelle dimension dans n’importe quelle Dimension dénombrable spécifique.

Exemple 1:

* Enième page dans une session - Dimension Page suivante
* La énième page d’un visiteur - Page suivante pour le visiteur - sur toutes les sessions
* Nième appel d’un utilisateur

Pourquoi est-il important de connaître le énième élément de la dimension dénombrable ?

* Vous souhaitez connaître la 5e page affichée dans une session.
* Vous souhaitez créer un chemin d’accès sur les campagnes afin de comprendre quelle campagne 2nd a été consultée après l’affichage de la campagne &quot;Compte de contrôle gratuit&quot; ?
* Vous souhaitez comprendre le lien sur lequel a cliqué le visiteur avant de cliquer sur le lien &quot;Chatter avec un agent&quot; ? ![](assets/dwb_impl_derived_dims7.png)

L’URI suivant est l’une des dimensions Maj de bureau qui peut être utilisée comme modèle. L’exemple ci-dessus vous donne l’élément 2e (Décalage = 1) de la campagne (Dim = Campagne) dans l’événement d’engagement (Clip = Événement d’engagement).

Ici, le décalage 1 signifie qu’il faut regarder à droite dans l’événement.

Autres Dimensions de déplacement hors limites

*Page suivante:*

Page suivante affichée dans une session après la page actuellement sélectionnée dans la Dimension de page

Ici, le décalage est de 1, le niveau est Page vue, la dimension est Page et le clip est Session

*Page précédente:*

Page précédente affichée dans une session avant la page actuellement sélectionnée dans la Dimension de page

Ici, le décalage est de -1, Niveau est Page vue, Dim est Page et Clip est Session

Quelle sera la campagne précédente affichée avant la campagne actuellement sélectionnée par un visiteur ?

Ici, le décalage est de -1, le niveau est réponse à la campagne, la dimension correspond à la valeur de l’attribut de réponse à la campagne et l’élément est Visiteur

*Création D’Une Dimension De Changement - Via Workstation*

* Marquer l’une des dimensions de déplacement OOB comme locale
* Renommer cette dimension avec un nom personnalisé
* Ouvrez la nouvelle dimension dans le poste de travail pour apporter des modifications.
* Modifiez les paramètres suivants de la dimension de mesure en fonction des exigences.

   * Dimension dénombrable de niveau
   * Décalage : vous souhaitez regarder vers l’avant vers l’arrière.
   * Dimension Dim dont vous souhaitez analyser les éléments
   * Clip-dénombrable dans que vous souhaitez afficher.

* Enregistrez la nouvelle dimension sur le serveur si vous souhaitez la partager avec d’autres personnes.

**Dernière Dimension N**

Les N dernières Dimensions s’appliquent uniquement à la Dimension Heure et à l’ Heure du système. Les dimensions d’heure OOB sont Jour, Semaine, Heure et Mois. Vous pouvez créer des dimensions, N dernières dimensions pour chacune de ces dimensions temporelles de base, telles que les 10 derniers jours, les 72 dernières heures, les 8 dernières semaines, les 6 derniers mois, etc. La Dernière Dimension N calcule la Dernière N en fonction de la &quot;mesure de la période du rapport&quot; actuelle ou de l’heure du système. ![](assets/dwb_impl_derived_dims8.png)

Nombre : nombre total d’éléments à afficher dans la dimension.

Décalage de plage : valeur du décalage indiquant le point de départ (Jour/Semaine) pour calculer les N derniers jours/Semaine.

**None.dim**

None.dim est une dimension Alias. Il est utilisé pour créer un alias à partir de dimensions étendues.

Exemple :

Dans le fichier None.dim, l’entité est définie comme &quot;wdata/model/dim/Parent/+name&quot; (elle peut être modifiée), ce qui signifie créer la dimension selon le nom du fichier de dimension. Ainsi, si nous créons une copie du fichier None.dim sous le dossier Dimension (par exemple, en copiant et en renommant le fichier None.dim sous le dossier Profil du visiteur) et en le renommant &quot;Log Source ID.dim&quot;, une nouvelle dimension dérivée avec l’ID Source du journal apparaîtra dans le menu sous Profil du visiteur, comme illustré ci-dessous :

Avant les modifications : ![](assets/dwb_impl_derived_dims9.png)

Après les modifications de None.dim : ![](assets/dwb_impl_derived_dims10.png)

L’entité peut être modifiée en nom de dimension étendu, dans ce cas, une autre dimension portant un autre nom pointant vers la même dimension, comme illustré ci-dessous :

Dans cet exemple, &quot;Source Name.dim&quot; comporte le contenu suivant : ![](assets/dwb_impl_derived_dims11.png)

Un autre nom de source de Dimension pointant vers l’ID de source de journal s’affiche. ![](assets/dwb_impl_derived_dims12.png)

**Masquage des Dimensions dérivées**

Pour masquer la Dimension dérivée, définissez la variable *Afficher* sur &quot;false&quot;. ![](assets/dwb_impl_derived_dims13.png)
