---
description: Le principal outil utilisé par les administrateurs système est le Gestionnaire de serveurs.
solution: Analytics
title: Gestionnaire des serveurs
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Gestionnaire des serveurs{#servers-manager}

Le principal outil utilisé par les administrateurs système est le Gestionnaire de serveurs.

Il s’agit de l’interface principale pour déterminer l’état général du système et pour exécuter des fonctions de configuration du système, de gestion des fichiers et de surveillance des erreurs.

Le Gestionnaire de serveurs affiche un point de couleur (noeud) pour chaque serveur et installation des outils de données [!DNL Sensor] dans votre système et fournit un aperçu de l’état du système pour chaque installation. Il affiche également un noeud pour votre installation des outils de données.

Les noeuds verts représentent les connexions actives, les noeuds rouges représentent les connexions désactivées ou inaccessibles, et les noeuds gris représentent les connexions dont l’état est indéterminé.

![](assets/vis_SysStat_RedGreenDots.png)

Un clic droit sur un noeud affiche des informations sur le composant de connexion et permet d’accéder à tous les menus associés.

Les tableaux suivants décrivent les informations fournies lorsque vous cliquez avec le bouton droit sur un noeud pour Outils de données, serveur Outils de données (y compris un serveur maître Outils de données dans une grappe) ou [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nom du produit, version et numéro de version. </p> <p>Exemple : Outils de données version 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>Adresse IP de l’ordinateur Outils de données. </p> <p>Exemple : 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurez le </p> </td> 
   <td colname="col2"> <p>Lien vers le fichier de <span class="keyword"> configuration de vos outils de </span> données. Cliquez sur <span class="uicontrol"> Configurer </span> &gt; <span class="uicontrol"> Insight.cfg </span> pour afficher la fenêtre de configuration des Outils de données. Toutes les modifications que vous apportez et enregistrez dans cette fenêtre sont répercutées dans le fichier <span class="filepath"> Insight.cfg </span> du répertoire d’installation des outils de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nom du produit, version et numéro de version. </p> <p>Exemple : Outils de données version 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Nom commun de l’ordinateur du serveur Outils de données. </p> <p>Exemple : <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>Adresse IP ou nom de domaine complet du serveur tel que configuré dans le fichier Adresses de l’ordinateur et le paramètre Emplacement réseau dans le fichier <span class="filepath"> Insight.cfg </span> . </p> <p>Exemple : 100.0.0.1 </p> <p>Pour plus d'informations sur le fichier Adresses, consultez le Guide <i>d'installation et d'administration des produits</i>serveur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État </p> </td> 
   <td colname="col2"> <p>Statut actuel du serveur Outils de données. Ce champ s’affiche lorsque le serveur Outils de données s’exécute normalement. Si une erreur s’est produite et que le noeud du serveur Outils de données est rouge, le champ affiche l’erreur (par exemple, "403 interdit"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Statut détaillé </p> </td> 
   <td colname="col2"> <p>Lien vers l’interface d’état <span class="keyword"> détaillé du serveur des outils de données </span> <span class="wintitle"> </span> qui permet de résoudre des erreurs ou d’autres problèmes avec le serveur des outils de données. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> L’interface</a>d’état détaillé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bureau à distance </p> </td> 
   <td colname="col2"> <p>Ouvre une session Bureau à <span class="wintitle"> distance </span> sur l’ordinateur du serveur Outils de données. </p> <p>Pour plus d'informations, voir <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> L'option Bureau à distance </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fichiers serveur </p> </td> 
   <td colname="col2"> <p>Lien vers le Gestionnaire de fichiers du <span class="wintitle"> serveur </span>, qui affiche les répertoires et les fichiers du répertoire d’installation du serveur Outils de données. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Le Gestionnaire de fichiers du serveur </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Moniteur du serveur </p> </td> 
   <td colname="col2"> <p>Lien vers l’ <span class="wintitle"> interface du moniteur du </span> serveur, utile pour le dépannage ou le suivi des paramètres de performances. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> L’interface du moniteur de serveur </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs associés </p> </td> 
   <td colname="col2"> <p>Pour les grappes de serveurs Outils de données uniquement. </p> <p>Menu répertoriant les noms communs des ordinateurs répertoriés dans le fichier *.address <span class="filepath"> du serveur maître </span> des outils de données. Cette liste inclut généralement tous les serveurs de traitement des <span class="keyword"> outils de données </span> de la grappe. Ce menu s’affiche uniquement si les Outils de données contiennent une copie du fichier *.address <span class="filepath"> du serveur maître </span> des outils de données. </p> <p>Lorsque vous cliquez sur <span class="uicontrol"> Serveurs </span>associés, vous pouvez cliquer sur l’une des options suivantes : 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Liste des moniteurs de serveur </span>, qui affiche la liste <span class="wintitle"> des détails de l’interface du moniteur de </span> serveur pour tous les serveurs associés </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Nom commun de tout serveur Outils de données, qui affiche un menu contextuel vous permettant d’ouvrir l’un des éléments suivants pour ce serveur particulier : 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Statut détaillé </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> L’Interface De Statut Détaillé </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Bureau à distance </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> L'Option Bureau À Distance </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Gestionnaire des fichiers serveur </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Le Gestionnaire De Fichiers Du Serveur </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Server Monitor </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> L’Interface Du Moniteur Du Serveur </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nom du produit, version et numéro de version. </p> <p>Exemple : Capteur 3.76; J3,67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> ID <span class="wintitle"> Sensor </span> spécifié dans le fichier de configuration <span class="wintitle"> Sensor </span> pour cette installation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Adresse IP du serveur Web ou d’applications sur lequel <span class="wintitle"> Sensor </span> est installé. </p> <p>Exemple : 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID de processus affecté par le système d’exploitation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Indique si <span class="wintitle"> Sensor </span> et le serveur Outils de données communiquent à l’aide de SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Heure </p> </td> 
   <td colname="col2"> <p>Heure (HH:MM:SS) que le <span class="wintitle"> capteur </span> a établi pour la dernière fois une connexion avec le serveur Outils de données. </p> </td> 
  </tr> 
 </tbody> 
</table>
