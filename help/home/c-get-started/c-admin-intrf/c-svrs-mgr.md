---
description: L’outil Principal utilisé par les administrateurs système est le Gestionnaire de serveurs.
title: Gestionnaire des serveurs
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Gestionnaire des serveurs{#servers-manager}

{{eol}}

L’outil Principal utilisé par les administrateurs système est le Gestionnaire de serveurs.

Il s’agit de la principale interface permettant de déterminer l’état global du système et d’exécuter des fonctions de configuration du système, de gestion des fichiers et de surveillance des erreurs.

Le Gestionnaire de serveurs affiche un point coloré (noeud) pour chaque serveur Data Workbench et [!DNL Sensor] installation dans votre système et fournit un état du système en un coup d’oeil pour chaque installation. Il affiche également un noeud pour votre installation de Data Workbench.

Les noeuds verts représentent des connexions principales, les noeuds rouges représentent des connexions désactivées ou inaccessibles, et les noeuds gris représentent des connexions dont l’état est indéterminée.

![](assets/vis_SysStat_RedGreenDots.png)

Cliquez avec le bouton droit de la souris sur un noeud pour afficher des informations sur le composant de connexion et accéder à tous les menus associés.

Les tableaux suivants décrivent les informations fournies lorsque vous cliquez avec le bouton droit sur un noeud pour Data Workbench, Data Workbench Server (y compris un serveur Data Workbench maître dans une grappe), ou [!DNL Sensor].

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
   <td colname="col2"> <p>Nom, version et numéro de build du produit. </p> <p>Exemple : Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>Adresse IP de l’ordinateur Data Workbench. </p> <p>Exemple : 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuration </p> </td> 
   <td colname="col2"> <p>Un lien vers votre <span class="keyword"> du Data Workbench </span> fichier de configuration. Cliquez sur <span class="uicontrol"> Configurer </span> &gt; <span class="uicontrol"> Insight.cfg </span> pour afficher la fenêtre de configuration du Data Workbench. Toutes les modifications que vous apportez et enregistrez dans cette fenêtre sont répercutées dans le <span class="filepath"> Insight.cfg </span> dans le répertoire d’installation de votre Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produit </p> </td> 
   <td colname="col2"> <p>Nom, version et numéro de build du produit. </p> <p>Exemple : Serveur Data Workbench 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Nom commun de l’ordinateur du serveur de Data Workbench. </p> <p>Exemple : <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adresse </p> </td> 
   <td colname="col2"> <p>Adresse IP ou nom de domaine complet du serveur tel que configuré dans le fichier d’adresses de l’ordinateur et le paramètre Emplacement réseau dans la variable <span class="filepath"> Insight.cfg </span> fichier . </p> <p>Exemple : 100.0.0.1 </p> <p>Pour plus d’informations sur le fichier Adresses, voir la section <i>Guide d’installation et d’administration des produits serveur</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>État </p> </td> 
   <td colname="col2"> <p>Etat actuel du serveur du Data Workbench. Ce champ affiche OK lorsque le serveur du Data Workbench s’exécute normalement. Si une erreur s’est produite et que le noeud du serveur de Data Workbench est rouge, le champ affiche l’erreur (par exemple, "403 Forbidden"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Statut détaillé </p> </td> 
   <td colname="col2"> <p>Un lien vers la variable <span class="keyword"> Serveur Data Workbench </span> <span class="wintitle"> Statut détaillé </span> qui s’avère utile pour résoudre les erreurs ou d’autres problèmes liés au serveur Data Workbench. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Interface de statut détaillée</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bureau à distance </p> </td> 
   <td colname="col2"> <p>Ouvre une <span class="wintitle"> Bureau à distance </span> session sur l’ordinateur du serveur de Data Workbench. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Option de bureau à distance </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fichiers de serveur </p> </td> 
   <td colname="col2"> <p>Un lien vers la variable <span class="wintitle"> Gestionnaire des fichiers de serveur </span>, qui affiche les répertoires et fichiers dans le répertoire d’installation du serveur de Data Workbench. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Gestionnaire des fichiers serveur </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Surveillance du serveur </p> </td> 
   <td colname="col2"> <p>Un lien vers la variable <span class="wintitle"> Surveillance du serveur </span> qui s’avère utile pour le dépannage ou le suivi des paramètres de performances. </p> <p>Pour plus d’informations, voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Interface du moniteur de serveur </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs associés </p> </td> 
   <td colname="col2"> <p>Pour les grappes de serveurs Data Workbench uniquement. </p> <p>Menu répertoriant les noms communs des ordinateurs répertoriés dans le gabarit <span class="filepath"> *.address du serveur Data Workbench </span> fichier . Cette liste inclut généralement l’ensemble du traitement <span class="keyword"> Serveurs Data Workbench </span> dans la grappe. Ce menu s’affiche uniquement si le Data Workbench dispose d’une copie du maître. <span class="filepath"> *.address du serveur Data Workbench </span> fichier . </p> <p>Lorsque vous cliquez sur <span class="uicontrol"> Serveurs associés </span>, vous pouvez cliquer sur l’une des options suivantes : 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Liste des moniteurs de serveur </span>, qui affiche le <span class="wintitle"> Surveillance du serveur </span> Liste des détails de l’interface pour tous les serveurs associés </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Nom commun de tout serveur de Data Workbench, qui affiche un menu contextuel vous permettant d’ouvrir l’un des éléments suivants pour ce serveur particulier : 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Statut détaillé </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Interface de statut détaillée </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Bureau à distance </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Option de bureau à distance </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Gestionnaire des fichiers de serveur </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Gestionnaire des fichiers serveur </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Surveillance du serveur </span>. Voir <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Interface du moniteur de serveur </a>. </li> 
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
   <td colname="col1"> <p>Produit </p> </td> 
   <td colname="col2"> <p>Nom, version et numéro de build du produit. </p> <p>Exemple : Capteur 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> Le <span class="wintitle"> Sensor </span> ID spécifié dans la variable <span class="wintitle"> Sensor </span> fichier de configuration de cette installation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Adresse IP du serveur web ou applicatif sur lequel <span class="wintitle"> Sensor </span> est installé. </p> <p>Exemple : 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID de processus attribué par le système d’exploitation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Si <span class="wintitle"> Sensor </span> et le serveur Data Workbench communique en utilisant SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Heure </p> </td> 
   <td colname="col2"> <p>Heure (HH):MM:SS) que la variable <span class="wintitle"> Sensor </span> a établi pour la dernière fois une connexion avec le serveur Data Workbench. </p> </td> 
  </tr> 
 </tbody> 
</table>
