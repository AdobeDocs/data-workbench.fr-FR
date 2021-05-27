---
description: Procédure de mappage du portail de rapports à un répertoire virtuel (IIS 7.0 ou supérieur).
title: Mappage du portail de rapports à un répertoire virtuel (IIS 7.0 ou supérieur)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# Mappage du portail de rapports à un répertoire virtuel (IIS 7.0 ou supérieur){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Procédure de mappage du portail de rapports à un répertoire virtuel (IIS 7.0 ou supérieur).

Actuellement, la plupart des clients Managed Service disposent de serveurs avec le système d’exploitation Windows Server 2008 et le serveur Web IIS 7.0 ou supérieur.

## Conditions préalables {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Assurez-vous que les composants ASP et [!DNL ASP.Net] sont installés pour IIS 7.0 ou version ultérieure.
* Assurez-vous que l&#39;utilisateur Web IIS a [!DNL Modify] accès au fichier [!DNL E:\Portal\data\users.mdb]. Vous pouvez le modifier en cliquant avec le bouton droit sur le fichier **[!UICONTROL users.mdb]** et, sous [!DNL Properties], accédez à l’onglet [!DNL Security]. Si vous ne voyez pas l&#39;utilisateur Web IIS répertorié ou si vous ne pouvez pas ajouter l&#39;utilisateur Web IIS à la liste, il vous suffit d&#39;accorder au groupe [!DNL Users] l&#39;accès [!DNL Modify].

* Assurez-vous que tout compte utilisateur utilisé pour exécuter [!DNL Application Pools] a également [!DNL Modify] accès aux dossiers [!DNL E:\Portal\data\users.mdb] et  [!DNL C:\Windows\Temp\] .

## Étapes d’installation {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Sur la machine sur laquelle [!DNL Report Portal] est installé, démarrez la balise [!DNL IIS Manager] :

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Sélectionnez **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Default Web Site]** et sélectionnez **[!UICONTROL Add Virtual Directory]**.

1. Pour un alias, saisissez Portal.
1. Pour le chemin physique, saisissez [!DNL E:\Portal\PortalASP].
1. Cliquez sur **[!UICONTROL OK]**.

   Le répertoire virtuel que vous avez créé apparaît sous [!DNL Default Web Site].

1. Ajoutez les répertoires virtuels suivants sous le répertoire virtuel que vous venez de créer.

   | Créez cet alias... | Pour cette ressource physique |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Images | [!DNL E:\Portal\PortalFiles\Images] |
   | Sortie | Emplacement physique du répertoire dans lequel [!DNL Report Server] enregistre la sortie pour vos jeux de rapports. Le dossier de sortie peut être situé n’importe où et peut être nommé comme n’importe quel dossier. Il contient un sous-dossier pour chaque jeu de rapports. Vous pouvez supprimer la balise [!DNL E:\Portal\PortalFiles\Output], mais déplacer la balise [!DNL profiles.xml] vers l’emplacement physique du fichier de sortie. |

1. Lorsque vous avez terminé, vérifiez qu’IIS affiche quatre nouveaux répertoires virtuels. Assurez-vous que la structure de répertoires comporte un dossier parent (portant le même nom que votre portail) et quatre sous-dossiers.
1. Cliquez sur **[!UICONTROL Application Pools]**, puis sur **[!UICONTROL DefaultAppPool]** (en supposant que c’est celui que vous avez configuré avec votre portail).

1. Cliquez sur **[!UICONTROL Advanced Settings]** et sélectionnez True pour activer les applications 32 bits.
1. Pour que [!DNL Portal] fonctionne, vous devez le convertir en application. Après avoir configuré les répertoires virtuels, cliquez avec le bouton droit sur le répertoire virtuel du portail et sélectionnez **[!UICONTROL Convert to Application]**.

## Conseils et astuces supplémentaires {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Vous pouvez télécharger le [!DNL Portal] à partir de Softdocs sous **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Vous pouvez simplement télécharger le [!DNL ReportPortal-Release-1-0-0-7.zip].

* Vous n’avez plus besoin de [!DNL ReportPortalSetup.xml], il peut donc être supprimé.
* Pour des raisons de normalisation, placez le contenu de ce fichier zip dans [!DNL E:\Portal].
* Pour déterminer le serveur SMTP Pour les clients de services gérés, vous pouvez aller ici.
* Insérez une requête avec NetOps afin de modifier l’entrée du nom de domaine dans IIS pour que le serveur de rapports soit plus convivial, par exemple [!DNL reports.clientname.insight.omniture.com], de sorte que l’URL globale de votre portail soit [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configurez votre fichier [!DNL email.asa] une fois cette modification mise en place.
