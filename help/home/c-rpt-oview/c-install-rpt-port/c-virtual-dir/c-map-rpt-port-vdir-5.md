---
description: Procédure de mappage du portail de rapports à un répertoire virtuel (IIS 5.0).
title: Mappage du portail de rapports à un répertoire virtuel (IIS 5.0)
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
exl-id: 20d8e9ea-c5b6-4a1b-9b15-557cc71ad5d9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# Mappage du portail de rapports à un répertoire virtuel (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

Procédure de mappage du portail de rapports à un répertoire virtuel (IIS 5.0).

1. Sur la machine où [!DNL Report Portal] est installé, démarrez le Gestionnaire des services Internet à l’aide de l’une des méthodes suivantes : **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** ou **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Sélectionnez **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Clic droit **[!UICONTROL Default Web Site]** et sélectionnez **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Lorsque la variable [!DNL Virtual Directory Wizard] s’ouvre, cliquez sur **[!UICONTROL Next]**.

1. Procédez comme suit pour définir le répertoire virtuel racine pour [!DNL Report Portal]:

   1. Lorsque vous êtes invité à saisir un alias, saisissez le nom de la variable [!DNL Report Portal], puis cliquez sur **[!UICONTROL Next]**. Par exemple, si vous souhaitez utiliser &quot;Portal&quot; comme nom de votre [!DNL Report Portal], affectez l’alias &quot;Portal&quot; au répertoire virtuel. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Next]**.

   1. Lorsque vous y êtes invité, recherchez et sélectionnez le chemin physique *&lt;**[!UICONTROL PortalName]**>* **[!UICONTROL \PortalASP]** , puis cliquez sur **[!UICONTROL Next]**.

      Exemple : [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Lorsque vous y êtes invité, vérifiez que les options suivantes sont activées :

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Cliquez sur **[!UICONTROL Next]**, puis sur **[!UICONTROL Finish]**. Le répertoire virtuel que vous avez créé s’affiche sous le site Web par défaut, comme illustré dans l’exemple suivant.

   ![](assets/RptPort_scrn_VirDirManual.png)

1. Cliquez avec le bouton droit sur le répertoire virtuel que vous venez de créer et sélectionnez **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Utilisez la variable [!DNL Virtual Directory] pour créer un alias pour chacun des répertoires physiques suivants. Cela permet de créer un répertoire virtuel nommé de manière appropriée pour chacune de ces ressources physiques.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Créez cet alias . . . </th> 
   <th colname="col2" class="entry"> Pour cette ressource physique . . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Base </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>Exemple : <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>Exemple : <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>Exemple : <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Images </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>Exemple : <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sortie </td> 
   <td colname="col2"> <p>Emplacement physique du répertoire dans lequel <span class="keyword"> Serveur de rapports</span> enregistre la sortie pour vos jeux de rapports. Le dossier de sortie peut être situé n’importe où, peut être nommé n’importe quel et contient un sous-dossier pour chaque jeu de rapports. </p> <p>Il doit s’agir du même répertoire que celui que vous spécifiez dans le paramètre Racine de sortie dans la variable <span class="filepath"> Report.cfg</span> pour un jeu de rapports. Pour plus d’informations, voir <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Configuration des fichiers Report.cfg</a>. </p> <p>L’emplacement par défaut est \<i>PortalName</i>\PortalFiles\Output. </p> <p>Exemple : <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>Le <i>PortalName</i>\PortalFiles\Output contient le répertoire <span class="filepath"> profiles.xml</span> qui doit être déplacé vers le répertoire de sortie que vous indiquez pour cet alias. </p> <p>Il est essentiel que la variable <span class="wintitle"> Chemin</span> est défini correctement. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Une fois que vous avez terminé, vérifiez qu’IIS affiche six nouveaux répertoires virtuels. Assurez-vous que la structure de répertoires comporte un dossier parent (portant le même nom que votre portail) et cinq sous-dossiers, comme illustré ci-dessous.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Lorsque vous avez terminé, accédez à [Modification du fichier de configuration de session](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) pour poursuivre le processus d’installation.
