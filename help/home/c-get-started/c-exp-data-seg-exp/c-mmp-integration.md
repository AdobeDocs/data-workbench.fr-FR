---
description: Data Workbench vous permet d’exporter des fichiers à intégrer à l’exportation de profils et d’audiences dans le cadre d’une Adobe Experience Cloud intégrée.
title: Exportation d’un profil marketing de Principal
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
exl-id: 9fc89815-d31d-41a7-a0c0-de1e84b24baa
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 3%

---

# Exportation d’un profil marketing de Principal{#master-marketing-profile-export}

Data Workbench vous permet d’exporter des fichiers à intégrer à Profiles et Audiences dans le cadre d’une Adobe Experience Cloud intégrée.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profils et audiences fait partie de [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr), un service principal de [!DNL Adobe Experience Cloud]. L’exportation de profils et d’audiences permet le partage d’audiences dans l’Experience Cloud à l’aide d’un identifiant Experience Cloud unique (ECID) attribué à chaque visiteur, puis utilisé par [Audience Manager](https://docs.adobe.com/content/help/fr-FR/experience-cloud/user-guides/home.html). L’application [!DNL ExportIntegration.exe] ( [!DNL E:\Server\Scripts]) est utilisée pour générer des exportations MMP et Adobe Target.

**Configuration du serveur FSU pour l’utilisation des profils et audiences**

1. Accédez à votre serveur FSU.
1. Ouvrez le fichier MMPExport.cfg . `Server/Admin/Export/MMPExport.cfg`.
1. Saisissez les valeurs dans tous les champs, au besoin. Par exemple :

   >[!NOTE]
   >
   >L’intégration MMP/AAM repose sur le compartiment s3 d’Amazon pour le transfert des données.
   >
   >
   >Les informations s3 requises pour le transfert MMP (s3) peuvent être obtenues auprès de l’équipe d’Audience Manager.

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >Le fichier [!DNL MMPExport.cfg]permet également de prendre tous les enregistrements, de les diviser en ensembles et de créer des blocs d&#39;enregistrements. Les blocs d’enregistrements sont ensuite exportés vers Amazon S3. Trois paramètres obligatoires sont requis pour créer des blocs d’enregistrements : [!DNL numRecordsPerChunk], [!DNL numThreads] et [!DNL maxRetriesOnSendFailure].

**Définition des paramètres**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Intervalle s3</i> </td> 
   <td colname="col2"> Compartiment AWS S3 vers lequel l’exportation est transférée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Object Directory</i> </td> 
   <td colname="col2"> Chemin d’accès pour l’enregistrement des fichiers s3. Cela prend en charge les sous-répertoires. <p> <p>Important :  Les caractères d’espace et multi-octets ne sont pas autorisés dans le chemin et créeront des erreurs dans l’exportation. (Le trait d’union est autorisé). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Region</i> </td> 
   <td colname="col2"> Région AWS s3 vers laquelle l’exportation est envoyée. Ex. us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Clé d’accès s3</i> </td> 
   <td colname="col2"> Clé d’accès AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Clé secrète s3</i> </td> 
   <td colname="col2"> Clé secrète AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>nom du fournisseur de données</i> </td> 
   <td colname="col2"> Il s’agit du nom de dossier utilisé pour stocker respectivement les segments et les caractéristiques dans AAM. Cette valeur doit être unique par client. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ID client</i> </td> 
   <td colname="col2"> Il s’agit d’un identifiant client unique fourni à un client lors de l’approvisionnement pour MMP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>secret client</i> </td> 
   <td colname="col2"> <p><i></i>Il s’agit d’un secret client unique fourni à un client lorsqu’il est configuré pour MMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> Nom d’utilisateur MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>password</i> </td> 
   <td colname="col2"> Mot de passe MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>Détermine la taille du bloc en termes de nombre d’enregistrements. </p> <p>L’implémentation coupe la valeur spécifiée par l’utilisateur à min = 1 000 records&amp;nbsp;(~50 KB chunks)&amp;nbsp;et max = 50 000 enregistrements (~2,5 MB chunks).&amp;nbsp;Une valeur par défaut de 10000 est utilisée lorsque l’utilisateur ne spécifie pas cette propriété de configuration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>Détermine le parallélisme de la partie d’envoi du bloc. Elle accepte une valeur comprise entre 1 et 24 threads, et sa valeur par défaut est 12 threads. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>Détermine le nombre de tentatives de reprise en cas d’échecs d’envoi de blocs. La valeur par défaut est 0 et ne spécifie aucune nouvelle tentative. </p> <p>L’intervalle de sommeil de 2 secondes est utilisé entre les reprises. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Génération de l’exportation MMP à partir du client**

1. Depuis le client, ouvrez un espace de travail et cliquez avec le bouton droit de la souris sur **[!UICONTROL Tools]** **[!UICONTROL Detail Table]**.
1. Ajoutez **Level**.
1. Cliquez avec le bouton droit sur l’en-tête et sélectionnez **Ajouter des attributs**.
1. Cliquez avec le bouton droit sur l’en-tête et sélectionnez **Nouvelle exportation de profil marketing de Principal**. ![](assets/mmp_mmp_export.png)
1. Développez **Requête**.

   ![](assets/mmp_mmp_query.png)

1. Développez **Configuration MMP**.
1. (obligatoire) Saisissez le **nom du segment MMP** et le **champ d’identifiant visiteur MMP**. Ces paramètres ne peuvent pas être laissés vides.
1. Le **nom du segment MMP** doit correspondre à l’identifiant de segment défini dans le MMP.
1. **L’identifiant visiteur MMP** est la colonne d’attributs définie à l’étape 4 qui correspond à l’**identifiant visiteur**.
1. Une fois ces champs renseignés, vous pouvez enregistrer l&#39;export avec le bouton droit de la souris sur l&#39;en-tête de l&#39;export et choisir **Enregistrer** comme &quot;Utilisateur\.export&quot;.
1. Ouvrez **Admin** > **Gestionnaire de profils** et enregistrez l’exportation dans le profil.

   Si toutes les données sont correctement saisies, un fichier d&#39;export sera généré dans le FSU ([!DNL Server/Exports]) et l&#39;export vers le AWS sera également transféré à l&#39;aide des informations de [!DNL MMPExport.cfg]. Le journal de cette opération est fourni dans [!DNL Server/Trace/]. par exemple, [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| Détails de la configuration | Description |
|---|---|
| Identifiant de segment MMP | Obligatoire. Il s’agit d’un identifiant que vous définiriez en premier dans l’Audience Manager. |
| Champ d’identifiant visiteur MMP | Mappez l’ECID. |
