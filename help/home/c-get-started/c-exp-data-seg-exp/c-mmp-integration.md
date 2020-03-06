---
description: Les outils de données vous permettent d’exporter des fichiers afin de les intégrer à l’exportation des profils et des audiences dans le cadre d’une intégration d’Adobe Experience Cloud.
title: Exportation du profil marketing parent
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Exportation du profil marketing parent{#master-marketing-profile-export}

Les outils de données vous permettent d’exporter des fichiers pour les intégrer aux profils et aux audiences dans le cadre d’un Adobe Experience Cloud intégré.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profils et audiences font partie du service [d’identité](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud [!DNL Adobe Experience Cloud], un service principal du. L’exportation Profils et audiences permet aux audiences d’être partagées dans Experience Cloud à l’aide d’un ECID (Experience Cloud ID) unique attribué à chaque visiteur, puis utilisé par [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html). L’ [!DNL ExportIntegration.exe] application ( [!DNL E:\Server\Scripts]) est utilisée pour générer des exportations MMP et Adobe Target.

**Configuration du serveur FSU pour utiliser les profils et audiences**

1. Accédez à votre serveur FSU.
1. Ouvrez le fichier MMPExport.cfg. `Server/Admin/Export/MMPExport.cfg`.
1. Entrez des valeurs dans tous les champs, le cas échéant. Par exemple :

   >[!NOTE]
   >
   >L’intégration MMP/AAM repose sur le compartiment s3 d’Amazon pour le transfert de données.
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
   >Le [!DNL MMPExport.cfg]fichier vous permet également de prendre tous les enregistrements, de les diviser en ensembles et de créer des morceaux d’enregistrements. Les blocs d’enregistrements sont ensuite exportés vers Amazon S3. Trois paramètres obligatoires sont requis pour créer des blocs d’enregistrements : [!DNL numRecordsPerChunk], [!DNL numThreads]et [!DNL maxRetriesOnSendFailure].

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
   <td colname="col1"> <i>s3 Bucket</i> </td> 
   <td colname="col2"> Le compartiment AWS S3 vers lequel l’exportation est transférée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Object Directory</i> </td> 
   <td colname="col2"> Chemin d’accès pour enregistrer les fichiers s3. Ceci prend en charge les sous-répertoires. <p> <p>Important :  Les caractères d’espace et les caractères multioctets ne sont pas autorisés dans le chemin d’accès et créeront des erreurs dans l’exportation. (Le trait d’union est autorisé). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Région</i> </td> 
   <td colname="col2"> Région AWS s3 vers laquelle l’exportation est envoyée. Ex. us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Clé d'accès s3</i> </td> 
   <td colname="col2"> Clé d’accès AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Clé secrète s3</i> </td> 
   <td colname="col2"> Clé secrète AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>nom du fournisseur de données</i> </td> 
   <td colname="col2"> Il s’agira du nom de dossier utilisé pour stocker les segments et les caractéristiques dans AAM, respectivement. Il doit être unique par client. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>ID client</i> </td> 
   <td colname="col2"> Il s’agit d’un identifiant client unique fourni à un client lorsqu’il est configuré pour MMP. </td> 
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
   <td colname="col2"> <p>Détermine la taille du bloc en termes de nombre d’enregistrements. </p> <p>L’implémentation clipe la valeur spécifiée par l’utilisateur sur min = 1000 enregistrements&amp;nbsp;(~50 Ko de blocs)&amp;nbsp;et max = 50000 enregistrements (~2,5 Mo de blocs).&amp;nbsp;Une valeur par défaut de 10000 est utilisée au cas où l'utilisateur ne spécifie pas cette propriété de configuration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>Détermine le parallélisme de la pièce d'envoi du fragment. Il accepte une valeur comprise entre 1 et 24 threads et sa valeur par défaut est 12 threads. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>Détermine le nombre de tentatives de nouvelle tentative en cas d’échec de l’envoi de blocs. La valeur par défaut est 0 pour ne pas spécifier de nouvelles tentatives. </p> <p>L’intervalle de veille de 2 secondes est utilisé entre les tentatives. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Génération de l’exportation MMP à partir du client**

1. Ouvrez un espace de travail à partir du client, puis cliquez avec le bouton droit de la souris **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**.
1. Ajouter un **niveau**.
1. Cliquez avec le bouton droit sur l’en-tête et sélectionnez **Ajouter des attributs**.
1. Cliquez avec le bouton droit sur l’en-tête et sélectionnez **Nouvelle exportation** de profil marketing principal. ![](assets/mmp_mmp_export.png)
1. Développez **Requête**.

   ![](assets/mmp_mmp_query.png)

1. Développez Configuration **MMP**.
1. (obligatoire) Saisissez le nom **du segment** MMP et le champ **ID du visiteur** MMP. Ces paramètres ne peuvent pas être laissés vides.
1. Le nom **du segment** MMP doit correspondre à l’ID du segment défini dans le MMP.
1. L’identifiant **visiteur** MMP est la colonne d’attributs définie à l’étape 4 qui correspond à l’identifiant **** visiteur.
1. Une fois ces champs saisis, vous pouvez enregistrer l&#39;exportation en cliquant avec le bouton droit de la souris sur l&#39;en-tête de l&#39;exportation et en choisissant **Enregistrer** comme &quot;Utilisateur\.Exporter&quot;.
1. Ouvrez **Admin** > Gestionnairede **profils** et enregistrez l’exportation dans le profil.

   Si toutes les données sont saisies correctement, un fichier d’exportation est généré dans le FSU ([!DNL Server/Exports]) et l’exportation est également transférée vers le AWS à l’aide des informations de [!DNL MMPExport.cfg]. Le journal correspondant est fourni dans [!DNL Server/Trace/]. par exemple, [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

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
| ID de segment MMP | Obligatoire. Il s’agit d’un identifiant que vous définiriez en premier dans Audience Manager. |
| Champ d’identifiant visiteur MMP | Faites correspondre l’ECID. |

