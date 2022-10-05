---
description: Le plan de travail vous permet d’organiser et d’accéder à tous vos espaces de travail et rapports.
title: Plans de travail
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Plans de travail{#worktops}

{{eol}}

Le plan de travail vous permet d’organiser et d’accéder à tous vos espaces de travail et rapports.

Dans la plupart des cas, la variable [!DNL Worktop] s’affiche immédiatement après l’ouverture de Data Workbench. Les fonctionnalités de [!DNL Worktop] inclure la barre latérale et l’interface à onglets. De plus, la barre latérale vous permet d’ajouter des visualisations et d’accéder aux fonctions utilisées régulièrement.

**Plan de travail**

![](assets/client-wktp.png)

Le [!DNL Worktop] vous permet également de créer et d’enregistrer des espaces de travail et des rapports nouveaux et mis à jour, ainsi que de publier des espaces de travail et des rapports sur le serveur de Data Workbench pour que d’autres utilisateurs puissent y accéder.

Le [!DNL Worktop] Le tableau d’éléments ci-dessous décrit chaque élément de la variable [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689">
 <tbody>
  <tr>
   <td colname="col1"> Barre latérale </td>
   <td colname="col2"> <p>La barre latérale fournit le contexte et le contrôle des espaces de travail, ainsi que la connaissance de l’état actuel d’un espace de travail et l’accès aux fonctions utilisées régulièrement. Les fonctions suivantes sont disponibles dans la barre latérale : </p> <p> <b>Connexion :</b> Indicateur d’état indiquant l’état en ligne. Cliquez sur l’état de connexion pour activer ou désactiver <span class="wintitle"> Travail en ligne</span>. Voir <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Travail hors ligne</a>. </p> <p> <b>Profil :</b> Indicateur du profil actif en cours d’utilisation. </p> <p> <b>À partir de : </b>Indicateur d’état indiquant la mise à jour des données dans le jeu de données du profil. Ces données sont téléchargées et traitées à partir du serveur DPU, ce qui ne peut se produire que lorsque vous travaillez en ligne. </p> <p> <b>Query/Sample Confidence :</b> Indicateur de la fin de la requête. Lorsque l’état demande à 100 %, toutes les données ont été interrogées. </p> <p> <b>Ajouter :</b> Permet d’ajouter des visualisations telles que des panneaux, des légendes et des tableaux à la barre latérale. Voir <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Ajout de visualisations à la barre latérale</a>. </p> <p> <b>Options :</b> Permet de revenir à un paramètre de la barre latérale précédente et de masquer automatiquement la barre latérale. </p> <p>Les paramètres de la barre latérale sont enregistrés dans la variable <span class="filepath"> sidebar.vw</span> lorsque vous fermez Data Workbench. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sous-répertoires de tabulation et de sous-onglet ou de liste déroulante (non affiché) </p> </td>
   <td colname="col2"> <p>Chaque onglet qui s’affiche sur la <span class="wintitle"> Workbench</span> correspond au <i>nom du profil de travail</i>\Workspaces\<i>nom de l’onglet</i> dans le répertoire d’installation du Data Workbench et représente un type particulier d’informations, telles que les tableaux de bord, l’activité, l’acquisition, les visiteurs, etc. Les sous-dossiers du dossier des noms d’onglet s’affichent par défaut sous forme de sous-onglets, mais ils peuvent également s’afficher sous forme de sous-répertoires. Voir <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Personnalisation des onglets du plan de travail</a>. </p> <p> <p>Remarque : Chaque profil de Data Workbench est fourni avec un ensemble standard d’onglets. Étant donné que votre mise en oeuvre peut être entièrement personnalisée, les espaces de travail (et, par conséquent, les onglets) qui s’affichent peuvent différer de ce qui est décrit dans ce guide. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> État du profil </td>
   <td colname="col2"> Fournit l’état de la connexion au serveur de Data Workbench et le nom du profil actuellement chargé. La date et l’heure "À partir de" pour les données du jeu de données du profil s’affichent sous l’indicateur en ligne. </td>
  </tr>
  <tr>
   <td colname="col1"> Minimiser, Maximiser, Fermer </td>
   <td colname="col2"> Fonctions Windows standard. </td>
  </tr>
  <tr>
   <td colname="col1"> Miniatures </td>
   <td colname="col2"> <p>Une miniature est un instantané d’un espace de travail qui s’affiche sur le <span class="wintitle"> Workbench</span>. Un nouvel instantané est pris chaque fois que vous enregistrez l’espace de travail. Les miniatures vous permettent d’identifier rapidement un espace de travail particulier sur la page <span class="wintitle"> Workbench</span>. </p> <p>Pour ouvrir un espace de travail, cliquez sur la miniature. </p> <p> <p>Remarque : Chaque profil de Data Workbench est fourni avec un ensemble standard d’espaces de travail. Étant donné que votre mise en oeuvre peut être entièrement personnalisée, les espaces de travail (et, par conséquent, les miniatures) qui s’affichent peuvent différer de ce qui est décrit dans ce guide. </p> </p> <p>Pour plus d’informations sur les espaces de travail, voir <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Configuration de la barre latérale</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Messages d’erreur </td>
   <td colname="col2"> <p>Les messages d’erreur s’affichent en rouge sous l’état . Pour consulter des descriptions de code d’état, voir <a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Par exemple : 403_Forbidden. </p> </td>
  </tr>
 </tbody>
</table>
