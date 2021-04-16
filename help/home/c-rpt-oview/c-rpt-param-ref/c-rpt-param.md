---
description: Informations sur les paramètres Report.cfg.
title: Paramètres Report.cfg
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2350'
ht-degree: 2%

---

# Paramètres Report.cfg{#report-cfg-parameters}

Informations sur les paramètres Report.cfg.

L&#39;exemple [!DNL Report.cfg] illustré dans [Configurer le jeu de rapports](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contient uniquement les paramètres inclus par défaut dans le fichier [!DNL Report.cfg]. Le tableau suivant décrit tous les paramètres de fichier [!DNL Report.cfg] disponibles.

Si vous devez ajouter des paramètres supplémentaires à un fichier [!DNL Report.cfg], vous devez le faire à l’aide d’un éditeur de texte. Pour connaître les étapes à suivre, y compris des exemples de définition de chaque entrée de paramètre, voir [Modification des fichiers Report.cfg existants](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>Les paramètres de ce tableau sont classés par ordre alphabétique. Lorsque vous ouvrez le fichier [!DNL Report.cfg] en Data Workbench, les vecteurs sont répertoriés par ordre alphabétique, suivi des paramètres individuels répertoriés par ordre alphabétique.

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Seuil d'alerte </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Ce paramètre s’applique uniquement aux rapports avec indicateurs de mesure. Nombre d'indicateurs de mesure qui doivent apparaître dans la feuille de calcul avant l'envoi d'un rapport d'alerte. </p> <p>Si une seule mesure est surveillée dans la feuille de calcul de l'indicateur de mesure, définissez le seuil sur 1. L'état est généré lorsque la mesure de la feuille est évaluée à une flèche vers le haut/vers le bas ou à un X. Si plusieurs mesures sont surveillées dans l'état, vous pouvez sélectionner le nombre d'indicateurs de mesure qui doivent être évalués à une flèche vers le haut/vers le bas ou à un X avant la génération de l'état. Par exemple, si deux mesures sont surveillées : 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Si le seuil est défini sur 1, le rapport est généré si l'une des mesures de la feuille est évaluée sur une flèche vers le haut/vers le bas ou sur un X. </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Si le seuil est défini sur 2, les deux mesures doivent être évaluées sur une flèche vers le haut/vers le bas ou sur un X avant la génération du rapport. </li> 
     </ul> </p> <p>Pour plus d'informations sur les indicateurs de mesure, consultez le <i>Guide de l'utilisateur Data Workbench</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Autoriser la régénération des rapports </td> 
   <td colname="col2"> <p>Indique si <span class="keyword"> Report Server </span> génère ou régénère automatiquement des rapports particuliers lorsque vous les créez ou les modifiez. Les options sont true ou false. Si ce paramètre est défini sur true, la création ou la modification d'un espace de travail de rapport entraîne la régénération de <span class="keyword"> Report Server </span> pour l'exécution la plus récente. </p> <p> <p>Remarque :  Si vous modifiez le fichier <span class="filepath"> Report.cfg </span>, <span class="keyword"> Report Server </span> régénère tous les rapports contrôlés par ce fichier <span class="filepath"> Report.cfg </span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pièces jointes </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Identifiant de section pour le nom et le type de contenu de toutes les pièces jointes qui sortent avec des rapports distribués par courrier électronique, y compris le nombre de pièces jointes. </p> <p>Pour ajouter une nouvelle pièce jointe : 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Ouvrez le fichier <span class="filepath"> Report.cfg </span> en Data Workbench. </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Cliquez avec le bouton droit <span class="uicontrol"> Pièces jointes </span> et cliquez sur <span class="uicontrol"> Ajouter un nouvel enfant </span> &gt; <span class="uicontrol"> Pièce jointe </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Type de contenu </td> 
   <td colname="col2"> <p>Type de contenu du fichier à joindre. </p> <p>Exemple : image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom de fichier </td> 
   <td colname="col2"> <p>Emplacement et nom du fichier à joindre. </p> <p>Exemple : <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Jeu de couleurs </td> 
   <td colname="col2"> Identifie le jeu de couleurs à utiliser pour les fichiers <span class="filepath"> .png </span>. 0 correspond à un fond noir ; 1 est destiné à un fond blanc ; et 2 correspond à une image en niveaux de gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commande à exécuter </td> 
   <td colname="col2"> <i>Facultatif</i>. Commande par lot ou exécutable qui s'exécute après la génération du jeu de rapports. Si le lancement de l'interpréteur de commandes shell est requis, faites précéder la commande de cmd /c. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle Excel par défaut </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Nom de fichier du fichier de modèle Excel générique ( <span class="filepath"> .xls </span> ou <span class="filepath"> .xlsx </span>) que vous souhaitez utiliser lors de la génération de rapports sous forme de fichiers Excel. Ce paramètre prend en charge les chemins d’accès aux fichiers complets, tels que <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Ce fichier est utilisé pour tous les rapports Excel, sauf si un modèle a été défini spécifiquement pour un rapport particulier. Voir <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Utilisation d'un fichier de modèle </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom de la dimension </td> 
   <td colname="col2"> <i>Facultatif</i>. Nom de la dimension pour laquelle vous souhaitez générer dynamiquement un rapport. Si vous saisissez un nom de dimension dans ce paramètre, vous devez entrer une valeur dans le paramètre Fichier de recherche ou dans les paramètres Mesure N supérieure et Valeur N supérieure. La dimension nommée dans ce paramètre doit exister dans le jeu de données pour lequel des rapports sont créés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Courriel uniquement si parfait </td> 
   <td colname="col2"> <i>Facultatif</i>. Permet à l’utilisateur de spécifier qu’un jeu de rapports doit être envoyé uniquement lorsqu’aucune erreur ne s’est produite au cours de l’exécution. Les options sont true et false. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Date de fin </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Date et heure auxquelles vous souhaitez que le rapport s'exécute en dernier. Cette heure est basée sur l’heure A partir du jeu de données. </p> <p>Format : Fuseau horaire MM/JJ/AAAA hh:mm, en utilisant la syntaxe des 24 heures pour l’heure </p> <p>Exemple : 08/01/2007 12:01 EDT </p> <p>Pour plus d'informations sur les paramètres de fuseau horaire, consultez le <i>Guide de configuration des ensembles de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tous les </td> 
   <td colname="col2"> Fréquence de la génération du jeu de rapports : jour, semaine ou mois. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Délai d’expiration d’Excel Watchdog (secondes) </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Nombre de secondes pendant lesquelles <span class="keyword"> Report Server </span> doit attendre que Microsoft Excel réponde lors de la génération d'un rapport sous la forme d'un fichier Excel avant <span class="keyword"> Report Server </span> qu'Excel ne répond pas et interrompt le processus. L’utilisation de ce paramètre permet à <span class="keyword"> Report Server </span> d’arrêter Excel lorsqu’il ne répond plus et de continuer à traiter vos rapports non Excel. La valeur par défaut est 300.0. Pour désactiver cette fonctionnalité, définissez ce paramètre sur 0.0. </p> <p>Assurez-vous que la valeur définie est suffisamment longue pour permettre l'exportation du rapport vers Excel. Sinon, <span class="keyword"> Report Server </span> peut arrêter prématurément Excel et votre rapport ne sera pas généré. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formule de filtre </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Filtre appliqué à chaque espace de travail du jeu de rapports. </p> <p>Pour plus d'informations, consultez la syntaxe <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> pour la création de filtres </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correction gamma </td> 
   <td colname="col2"> <p>Paramètre Gamma pour la sortie de fichier <span class="filepath"> .png </span>. La valeur par défaut est de 1.6. </p> <p> <p>Remarque :  Adobe recommande de ne pas modifier cette valeur. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masquer les logos </td> 
   <td colname="col2"> Indique si le serveur de rapports masque les logos lors de la génération des rapports. Les options sont <span class="filepath"> true </span> ou <span class="filepath"> false </span>. Si la variable est définie sur <span class="filepath"> false </span>, votre rapport est généré avec le logo du rapport. La valeur par défaut est <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de recherche </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Lorsque ce paramètre est renseigné, le serveur de rapports s’exécute en mode dynamique et génère des rapports pour chaque élément de la dimension spécifié dans le paramètre Nom de la Dimension. Ce fichier doit contenir deux colonnes délimitées par des tabulations, sans rangée d’en-tête. </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">La colonne 1 contient une liste d'éléments de dimension. </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">La colonne 2 contient les adresses électroniques des destinataires de rapports. Un rapport pour un élément donné de la colonne 1 est envoyé à l’adresse électronique sur la même ligne de la colonne 2. Vous pouvez entrer plusieurs adresses électroniques en les séparant par des virgules (sans espace). Si les rapports ne doivent pas être envoyés par courriel, cette colonne peut être vide mais doit exister. </li> 
     </ul> </p> <p> <p>Remarque :  Si vous entrez une valeur dans ce paramètre, vous devez en saisir une dans le paramètre Nom de la Dimension. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Notification uniquement </td> 
   <td colname="col2"> Ce paramètre <span class="wintitle"> Serveur de rapports </span> vous permet de configurer l'outil de données pour envoyer un courrier électronique lorsqu'un rapport est généré. La définition de cette valeur sur <span class="filepath"> true </span> n’envoie pas le rapport, mais envoie plutôt un courrier électronique informant l’utilisateur abonné que le rapport a été généré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapport Courrier </td> 
   <td colname="col2"> <p>Identifiant de section pour la distribution des rapports par courrier électronique. Pour distribuer les rapports par courriel, remplissez les paramètres suivants pour l'entrée <span class="wintitle"> Rapport de courrier </span>. Tous les rapports du jeu de rapports sont envoyés par courriel en un seul message aux adresses électroniques spécifiées dans le paramètre Destinataire. </p> <p> <p>Remarque :  Le serveur de rapports n’envoie un courrier électronique que lorsqu’il a généré au moins un rapport. </p> </p> <p>Pour activer l'envoi par courriel des rapports, vous devez au moins remplir les paramètres suivants pour cette entrée : 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">Serveur SMTP </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Destinataires </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Adresse de l'expéditeur </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Notification uniquement </li> 
     </ul> </p> <p> <p>Remarque :  Pour envoyer des rapports par courriel après avoir recréé un jeu de rapports, voir <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Modification des fichiers du fichier Report.cfg existant </a>. </p> </p> <p>La valeur Notification seulement est disponible dans les versions 5.4x et 5.5x. </p> <p>Pour qu’un grand nombre de destinataires soient avertis (plus de 20), il est vivement recommandé d’utiliser des listes de distribution par courrier électronique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle XSL de contenu </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Chemin du fichier de modèle XSL à appliquer au fichier <span class="filepath"> reports.xml </span>. L’utilisation de ce paramètre permet au serveur de rapports d’envoyer vos rapports dans le courrier électronique distribué plutôt que sous forme de pièces jointes. Le texte qui en résulte est utilisé comme corps du message électronique. </p> <p>Voir <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Fichiers d’exemple de rapport </a> pour un fichier d’exemple. </p> <p>Pour plus d'informations sur le langage XSLT (Extensible Stylesheet Language), voir <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> The Extensible Stylesheet Language Family </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Destinataires </td> 
   <td colname="col2"> Adresses électroniques des personnes auxquelles vous souhaitez envoyer le rapport. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse de l'expéditeur </td> 
   <td colname="col2"> Adresse électronique de l’expéditeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom de l'expéditeur </td> 
   <td colname="col2"> Facultatif. Nom de l'expéditeur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveur SMTP </td> 
   <td colname="col2"> Adresse du serveur SMTP et mot de passe et nom d’utilisateur requis pour l’authentification. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Objet </td> 
   <td colname="col2"> <i>Facultatif</i>. Objet décrivant le courrier électronique à envoyer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Notification uniquement </td> 
   <td colname="col2"> Permet de configurer l’outil de données pour envoyer un courrier électronique lorsqu’un rapport d’arrière-plan est généré. La définition de cette valeur sur True n'envoie pas le rapport, mais envoie plutôt un courrier électronique reliant l'utilisateur abonné à l'emplacement du rapport. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Racine de sortie </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Emplacement de sortie des jeux de rapports générés. Le dossier par défaut est <i>&lt;nom du profil&gt;</i>\Reports dans le répertoire d’installation du serveur de rapports. </p> <p>Pour configurer <span class="keyword"> Report Server </span> de manière à générer des rapports sur un portail, définissez <span class="wintitle"> Racine de sortie </span> sur la racine de document du serveur Web utilisé pour le portail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtre de Requête de préchargement </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Ce paramètre s’applique uniquement au type de rapport <span class="wintitle"> Elément de Dimension supérieure </span>. </p> <p>Nom du filtre à appliquer à la requête qui doit être exécutée pour déterminer les N principaux éléments de dimension avant de pouvoir générer le rapport. La valeur par défaut est <span class="wintitle"> Broken_Session_Filter </span>. Pour plus d'informations sur le <span class="wintitle"> filtre de session rompue </span>, consultez le <i>Guide de l'utilisateur Data Workbench</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Types de rapports </span> </td> 
   <td colname="col2"> <p>Format(s) dans lequel vous souhaitez générer votre sortie. Vous pouvez utiliser l’une des options suivantes ou toutes les options suivantes pour générer le jeu de rapports dans plusieurs formats simultanément : 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel crée un classeur Excel avec une visualisation par feuille de calcul. En règle générale, utilisez des fichiers Excel pour la distribution des courriers électroniques. Voir <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Génération de rapports sous forme de fichiers Microsoft Excel </a>. Pour plus d'informations sur l'utilisation d'un fichier de modèle, voir <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Utilisation d'un fichier de modèle </a>. </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png crée des fichiers Portable Network Graphic. En règle générale, utilisez des fichiers <span class="filepath"> .png </span> pour l’affichage dans un navigateur Web (portail). </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">La miniature crée une miniature ( <span class="filepath"> fichier .jpg </span>) de l’espace de travail. La taille par défaut est de 240 x 180. Pour modifier la taille par défaut, modifiez les paramètres Miniature X et Miniature Y. </li> 
     </ul> </p> <p>Pour ajouter un nouveau type de rapport lors de la modification de <span class="filepath"> Report.cfg </span> dans l'outil de données, cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Types de rapports </span>, cliquez sur <span class="uicontrol"> Ajouter un nouvel enfant </span> et sélectionnez le type de rapport souhaité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Date de début </td> 
   <td colname="col2"> <p>Date et heure auxquelles vous souhaitez que le rapport s'exécute pour la première fois. Cette heure est basée sur l’heure A partir du jeu de données. </p> <p>Format : Fuseau horaire MM/JJ/AAAA hh:mm, en utilisant la syntaxe de 24 heures. </p> <p>Pour plus d'informations sur les paramètres de fuseau horaire, consultez le <i>Guide de configuration des ensembles de données</i>. </p> <p> <p>Remarque :  Les rapports s’exécutent lorsque les horodatages des données du profil correspondent à la date et à l’heure spécifiées. </p> </p> <p>Exemple : </p> <p>Si la date du début est le 08/08/2006 à 12h00 (HNE), les rapports s’exécutent pour les données avec un horodatage de 08/08/2006 à 12h00 (HNE) et plus tard. 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">Les rapports quotidiens seront exécutés pour le 08/08/2006 et, par la suite, chaque jour pour les données avec hh:mm = 12:00 HNE. </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">Les rapports hebdomadaires s'exécuteront pour le 08/08/2006 et pour chaque 7e jour suivant pour les données avec hh:mm = 12:00 EST. </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">Les rapports mensuels seront exécutés pour le 08/08/2006 et pour le 8e jour de chaque mois par la suite pour les données avec hh:mm = 12:00 EST. </li> 
     </ul> </p> <p>La mesure <span class="wintitle"> Heure du rapport </span> affecte les dimensions "N dernier" rapports, telles que "7 derniers jours", "Hier" et "3 semaines auparavant". Pour les requêtes du serveur de rapports, la mesure <span class="wintitle"> Heure du rapport </span> ( <span class="filepath"> Temps du rapport </span>) identifie la date et l’heure d’exécution des rapports. Il s’agit initialement de la date et de l’heure spécifiées dans le paramètre Date de Début, qui s’incrémente ensuite selon la période spécifiée par le paramètre Chaque. Pour les requêtes des outils de données, la mesure <span class="wintitle"> Heure du rapport </span> est basée sur minuit de la mesure A partir de ( <span class="filepath"> A partir de </span> mesure ). En raison de la différence de définitions de la mesure Temps des rapports, si vous requête un espace de travail qui utilise une dimension N dernier, vous pouvez recevoir des résultats différents dans les outils de données et <span class="keyword"> Serveur de rapports </span> pour le même espace de travail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniature X </td> 
   <td colname="col2"> <i>Facultatif</i>. Entier contrôlant la taille (en pixels) de l’axe X des miniatures générées en tant que sortie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniature Y </td> 
   <td colname="col2"> <i>Facultatif</i>. Entier contrôlant la taille (en pixels) de l’axe Y des miniatures générées en tant que sortie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure N supérieure </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Voir la description du paramètre N valeur supérieure. </p> <p> <p>Remarque :  Si vous entrez une valeur dans ce paramètre, vous devez entrer une valeur dans le paramètre Nom de la Dimension et N Valeur supérieure. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> N valeur supérieure </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Lorsque ce paramètre est renseigné, <span class="keyword"> Report Server </span> s’exécute en mode dynamique et génère des rapports pour le nombre supérieur (spécifié dans ce paramètre) d’éléments pour la dimension spécifiée dans le paramètre Nom de la Dimension, en comptant par la mesure spécifiée dans le paramètre Mesure N supérieure. </p> <p>Exemple : Si vous saisissez Page dans le paramètre Nom de la Dimension, Sessions dans le paramètre Mesure N supérieure et 5 dans ce paramètre, le rapport généré liste les cinq pages principales ayant le plus grand nombre de sessions. </p> <p> <p>Remarque :  Si vous entrez une valeur dans ce paramètre, vous devez entrer une valeur dans le paramètre Nom de la Dimension et le paramètre Mesure N supérieure. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utiliser un exemple local uniquement </td> 
   <td colname="col2"> <i>Facultatif</i>. Indique si vous souhaitez que <span class="keyword"> Report Server </span> génère des rapports en utilisant uniquement l’échantillon local du jeu de données. La définition de ce paramètre sur true vous permet de vue d’un échantillon du jeu de rapports (sans charger un serveur de l’outil de données) pour voir à quoi ressemble la sortie sans prendre tout le temps nécessaire pour traiter les données. Il s'agit d'une fonction de test. Les options sont true ou false. La valeur par défaut est false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Chemin de l’espace de travail </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Emplacement d’une collection d’espaces de travail pour un jeu de rapports donné. Cela s’avère utile pour gérer une seule copie des espaces de travail qui doivent être générés et distribués de plusieurs manières, en utilisant les fichiers <span class="filepath"> Report.cfg </span> pour plusieurs jeux de rapports. Le répertoire racine de ce chemin d’accès peut être n’importe quel dossier de profil. N’entrez pas de barre oblique (\) en début de la chaîne de chemin. </p> <p>Exemple : Vous pouvez enregistrer les espaces de travail communs pour les ensembles A et B dans le dossier <span class="filepath"> Reports\Common </span>, puis définir les fichiers <span class="filepath"> Report.cfg </span> pour deux jeux de rapports différents, chacun avec des paramètres de génération et de distribution différents. Dans les deux fichiers <span class="filepath"> Report.cfg </span>, vous définissez le paramètre Chemin d’accès à l’espace de travail sur <i>nom du profil</i>\Reports\Common. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de sortie XSL </td> 
   <td colname="col2"> <i>Facultatif</i>. Chemin du fichier de sortie créé lorsque le modèle XSL </span> est appliqué à l'index de rapport.<span class="wintitle"> </span></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modèle XSL </td> 
   <td colname="col2"> <p><i>Facultatif</i>. Chemin d’accès au fichier de modèle XSL à appliquer à l’index de rapport. Le fichier de sortie XSL <span class="filepath"> .xml </span> transformé qui en résulte est écrit dans le <span class="wintitle"> fichier de sortie XSL </span> spécifié. Voir <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Fichiers d’exemple de rapport </a> pour un fichier d’exemple. </p> <p> <p>Remarque :  À moins que vous n'utilisiez un modèle <span class="filepath"> .xsl </span> lors de la génération de vos rapports, tous les rapports sont distribués par courrier électronique sous forme de pièces jointes. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
