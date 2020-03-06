---
description: Worktop vous permet d’organiser et d’accéder à tous vos espaces de travail et rapports.
solution: Analytics
title: Classeurs
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Classeurs{#worktops}

Worktop vous permet d’organiser et d’accéder à tous vos espaces de travail et rapports.

Dans la plupart des cas, le [!DNL Worktop] rapport s’affiche immédiatement après l’ouverture des Outils de données. Les fonctionnalités de [!DNL Worktop] cette interface incluent l’encadré et l’interface à onglets. De plus, la barre latérale vous permet d’ajouter des visualisations et d’accéder aux fonctions régulièrement utilisées.

**Workbench**

![](assets/client-wktp.png)

Il [!DNL Worktop] permet également de créer et d’enregistrer des espaces de travail et des rapports nouveaux et mis à jour, ainsi que de publier des espaces de travail et des rapports sur le serveur Outils de données pour que d’autres puissent y accéder.

Le tableau [!DNL Worktop] d’éléments ci-dessous décrit chaque élément du [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Barre latérale </td> 
   <td colname="col2"> <p>La barre latérale fournit le contexte et le contrôle des espaces de travail, ainsi que la connaissance de l’état actuel d’un espace de travail et l’accès aux fonctions utilisées régulièrement. Les fonctions suivantes sont disponibles dans la barre latérale : </p> <p> <b>Connexion :</b> Indicateur d’état indiquant l’état en ligne. Cliquez sur l'état de la connexion pour activer ou désactiver <span class="wintitle"> Travailler en ligne</span>. Voir <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Travail hors connexion et en ligne</a>. </p> <p> <b>Profil :</b> Indicateur du profil en cours d’utilisation. </p> <p> <b>A partir de : </b>Indicateur d’état indiquant la mise à jour des données dans le jeu de données du profil. Ces données sont téléchargées et traitées à partir du serveur DPU, ce qui ne peut se produire que lorsque vous travaillez en ligne. </p> <p> <b>Requête/Exemple de fiabilité :</b> Indicateur de la fin de la requête. Lorsque l’état interroge à 100 %, toutes les données ont été interrogées. </p> <p> <b>Ajouter :</b> Vous permet d’ajouter des visualisations telles que des panneaux, des légendes et des tableaux à la barre latérale. Voir <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Ajout de visualisations à la barre latérale</a>. </p> <p> <b>Options :</b> Permet de rétablir un paramètre de barre latérale précédent et de masquer automatiquement la barre latérale. </p> <p>Les paramètres de l’encadré sont enregistrés dans le fichier <span class="filepath"> sidebar.vw</span> lorsque vous fermez Outils de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sous-répertoires Tabulation et Sous-onglet ou Liste déroulante (non affichée) </p> </td> 
   <td colname="col2"> <p>Chaque onglet qui s’affiche sur <span class="wintitle"> Worktop</span> correspond au nom <i>du profil de</i>travail de l’onglet \Workspaces\<i>du dossier de nom</i> de l’onglet dans le répertoire d’installation des Outils de données et représente un type particulier d’informations, telles que les tableaux de bord, l’activité, les acquisitions, les visiteurs, etc. Les sous-dossiers du dossier des noms d’onglet s’affichent par défaut sous forme de sous-onglets, mais ils peuvent également être affichés sous forme de sous-répertoires. Voir <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Personnalisation des onglets</a>de Worktop. </p> <p> <p>Remarque :  Chaque profil Outils de données est fourni avec un ensemble standard d’onglets. Comme votre implémentation peut être entièrement personnalisée, les espaces de travail (et, par conséquent, les onglets) qui s’affichent peuvent différer de ce qui est décrit dans ce guide. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Statut du profil </td> 
   <td colname="col2"> Fournit l’état de la connexion au serveur Outils de données et le nom du profil actuellement chargé. La date et l’heure A partir de la date et l’heure des données du jeu de données du profil s’affichent sous l’indicateur en ligne. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimiser, Maximiser, Fermer </td> 
   <td colname="col2"> Fonctions Windows standard. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatures </td> 
   <td colname="col2"> <p>Une miniature est un instantané d’un espace de travail qui s’affiche sur <span class="wintitle"> Worktop</span>. Un nouvel instantané est pris chaque fois que vous enregistrez l’espace de travail. Les miniatures vous permettent d’identifier rapidement un espace de travail particulier sur le <span class="wintitle"> plan de travail</span>. </p> <p>Pour ouvrir un espace de travail, cliquez sur la miniature. </p> <p> <p>Remarque :  Chaque profil Outils de données est fourni avec un ensemble standard d’espaces de travail. Comme votre implémentation peut être entièrement personnalisée, les espaces de travail (et, par conséquent, les miniatures) qui apparaissent peuvent différer de ce qui est décrit dans ce guide. </p> </p> <p>Pour plus d’informations sur les espaces de travail, voir <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Configuration de la barre latérale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Messages d’erreur </td> 
   <td colname="col2"> <p>Les messages d’erreur s’affichent en rouge sous l’état. Pour obtenir des descriptions de code d’état, voir <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Par exemple : 403_Interdit. </p> </td> 
  </tr> 
 </tbody> 
</table>

