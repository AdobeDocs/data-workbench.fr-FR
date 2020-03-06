---
description: Cette section décrit la procédure à suivre pour mapper le portail de rapports à un répertoire virtuel (IIS 7.0 ou version ultérieure).
solution: Analytics
title: Mappage du portail de rapports à un répertoire virtuel (IIS 7.0 ou version ultérieure)
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappage du portail de rapports à un répertoire virtuel (IIS 7.0 ou version ultérieure){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Cette section décrit la procédure à suivre pour mapper le portail de rapports à un répertoire virtuel (IIS 7.0 ou version ultérieure).

Actuellement, la plupart des clients du service géré disposent de serveurs avec le système d’exploitation Windows Server 2008 et le serveur Web IIS 7.0 ou version ultérieure.

## Conditions préalables {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Assurez-vous que ASP et [!DNL ASP.Net] les composants sont installés pour IIS 7.0 ou version ultérieure.
* Assurez-vous que l&#39;utilisateur Web IIS a [!DNL Modify] accès au [!DNL E:\Portal\data\users.mdb] fichier. Vous pouvez changer cela en cliquant avec le bouton droit sur le **[!UICONTROL users.mdb]** fichier et sous [!DNL Properties], accédez à l&#39; [!DNL Security] onglet. Si l&#39;utilisateur Web IIS n&#39;est pas répertorié ou si vous n&#39;avez pas la possibilité d&#39;ajouter l&#39;utilisateur Web IIS à la liste, donnez simplement au [!DNL Users] groupe l&#39; [!DNL Modify] accès.

* Assurez-vous que tout compte utilisateur utilisé pour exécuter le [!DNL Application Pools] a également [!DNL Modify] accès aux dossiers [!DNL E:\Portal\data\users.mdb] et [!DNL C:\Windows\Temp\].

## Étapes d’installation {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Sur l’ordinateur sur lequel [!DNL Report Portal] est installé, démarrez [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Cliquez avec le bouton droit **[!UICONTROL Default Web Site]** et sélectionnez **[!UICONTROL Add Virtual Directory]**.

1. Pour un alias, saisissez Portal.
1. Pour le chemin physique, entrez [!DNL E:\Portal\PortalASP].
1. Cliquez sur **[!UICONTROL OK]**.

   Le répertoire virtuel que vous avez créé s’affiche sous [!DNL Default Web Site].

1. Ajoutez les répertoires virtuels suivants sous le répertoire virtuel que vous venez de créer.

   | Créer cet alias... | Pour cette ressource physique |
   |---|---|
   | Base | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Images | [!DNL E:\Portal\PortalFiles\Images] |
   | Sortie | Emplacement physique du répertoire dans lequel [!DNL Report Server] enregistre la sortie pour vos jeux de rapports. Le dossier de sortie peut se trouver n’importe où et peut être nommé n’importe quel nom. Il contient un sous-dossier pour chaque jeu de rapports. Vous pouvez supprimer le fichier [!DNL E:\Portal\PortalFiles\Output], mais déplacer [!DNL profiles.xml] le fichier vers son emplacement physique. |

1. Une fois terminé, vérifiez qu’IIS affiche quatre nouveaux répertoires virtuels. Assurez-vous que la structure de répertoires comporte un dossier parent (portant le même nom que votre portail) et quatre sous-dossiers.
1. Cliquez sur **[!UICONTROL Application Pools]**, puis **[!UICONTROL DefaultAppPool]** (en supposant que c&#39;est celui que vous avez configuré avec votre portail).

1. Cliquez sur **[!UICONTROL Advanced Settings]** et sélectionnez True pour activer les applications 32 bits.
1. Pour que le [!DNL Portal] logiciel fonctionne, vous devez le convertir en application. Après avoir configuré les répertoires virtuels, cliquez avec le bouton droit sur le répertoire virtuel Portal et sélectionnez **[!UICONTROL Convert to Application]**.

## Conseils et astuces supplémentaires {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Vous pouvez télécharger le [!DNL Portal] depuis Softdocs sous **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Vous pouvez simplement télécharger le [!DNL ReportPortal-Release-1-0-0-7.zip].

* Vous n’avez plus besoin de la [!DNL ReportPortalSetup.xml], donc elle peut être supprimée.
* Dans un souci de standardisation, placez le contenu de ce fichier zip dans [!DNL E:\Portal].
* Pour déterminer le serveur SMTP Pour les clients de services gérés, vous pouvez aller ici.
* Placez une requête avec NetOps pour modifier l’entrée du nom de domaine dans IIS pour le serveur de rapports en quelque chose de plus convivial, par exemple [!DNL reports.clientname.insight.omniture.com], de sorte que l’URL globale du portail soit [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configurez votre [!DNL email.asa] fichier une fois cette modification mise en place.

