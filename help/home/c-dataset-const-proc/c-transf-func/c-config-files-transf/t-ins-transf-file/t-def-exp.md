---
description: Les exportateurs fournissent les instructions pour envoyer les données d’événement.
solution: Analytics
title: Définition des exportateurs
topic: Data workbench
uuid: 565d4482-6c25-407c-bda7-0d116180902a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Définition des exportateurs{#defining-exporters}

Les exportateurs fournissent les instructions pour envoyer les données d’événement.

La fonctionnalité de transformation fournit trois types d’exportateurs pour exporter [!DNL .vsl] des fichiers, des fichiers journaux, des fichiers XML et des données ODBC sous forme de [!DNL .vsl] fichiers, de fichiers texte ou de fichiers texte délimités pouvant être utilisés par les routines de chargement de DataWarehouse, les agences de contrôle ou d’autres cibles.

>[!NOTE]
>
>Pour qu’un exportateur fonctionne correctement, la source du journal doit répondre aux exigences appropriées décrites dans la section Sources [du](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) journal du fichier [de configuration de traitement du](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)journal.

**Pour définir un exportateur**

1. Ouvrez [!DNL Transform.cfg] dans les outils de données. Voir [Pour modifier le fichier](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13)Insight Transform.cfg.
1. Cliquez avec le bouton droit **[!UICONTROL Exporters]**, puis cliquez **[!UICONTROL Add New]**.
1. Sélectionnez l’une des options suivantes :

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**
   >[!NOTE]
   >
   >Pour cette [!DNL ExportVSLFile] option, tous les champs étendus du fichier d’entrée et tous les champs définis par l’utilisateur du formulaire cs(*header*) sont toujours écrits dans le fichier de sortie VSL. Si vous remplacez un champ étendu existant, la nouvelle valeur est écrite dans le fichier de sortie, même si le champ est vide.

1. Modifiez les paramètres Exporters dans le fichier de configuration à l’aide du tableau suivant comme guide :

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Format des données </td> 
      <td colname="col2"> <p>Pour <span class="wintitle"> ExportTextFile</span> uniquement. Format de chaque ligne de sortie, composé d’échappement de nom de champ (exprimé sous la forme %<i>fieldname</i>%) et de tout autre texte fixe souhaité. Le format doit inclure un séparateur de ligne, généralement [CR] [LF]. </p> <p> Un signe de pourcentage littéral (%) peut être incorporé dans la chaîne de format en échappant le caractère comme illustré ici : %% </p> <p> Un exemple d’entrée pour le paramètre Format de données est <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Champs </td> 
      <td colname="col2">Pour <span class="wintitle"> ExportDelimitedTextFile</span> uniquement. Noms des champs à générer. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Délimiteur </td> 
      <td colname="col2"> <p>Facultatif. Pour <span class="wintitle"> ExportDelimitedTextFile</span> uniquement. Caractère utilisé pour séparer les champs du fichier de sortie. </p> <p> Le logiciel ne peut pas ignorer les délimiteurs inclus dans les valeurs des données. Par conséquent, Adobe recommande de ne pas utiliser de virgules comme délimiteurs. </p> <p> Si vous maintenez la touche Ctrl enfoncée et cliquez avec le bouton droit dans le paramètre Délimiteur, un menu <span class="wintitle"> Insertion</span> s'affiche. Ce menu contient une liste de caractères spéciaux qui sont souvent utilisés comme délimiteurs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Séparateur de ligne </td> 
      <td colname="col2">Facultatif. Pour <span class="wintitle"> ExportDelimitedTextFile</span> uniquement. Caractère(s) utilisé(s) pour séparer les lignes dans les fichiers de sortie. La valeur par défaut est [CR] [LF]. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Nom </td> 
      <td colname="col2"> <p>Facultatif. Identifiant de l'exportateur. Ce nom apparaît dans l’interface État <span class="wintitle"></span> détaillé. </p> <p> Pour plus d’informations sur l’interface d’état <span class="wintitle"> détaillé, consultez le Guide</span> de l’utilisateur des outils de <i></i>données. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Commentaires </td> 
      <td colname="col2"> Facultatif. Remarques sur l'exportateur. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Chemin de sortie </td> 
      <td colname="col2"> <p>Chemin d’accès où les fichiers de sortie doivent être stockés. Le chemin d’accès est relatif au dossier d’installation du serveur de l’outil de données. </p> <p> <p>Remarque : Le serveur des outils de données qui stocke les données de sortie est le serveur de traitement n° 0 dans le fichier <span class="filepath"> .cfg</span> profile. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Période de rotation du fichier </td> 
      <td colname="col2"> <p>Facultatif. Fréquence à laquelle les données sont exportées dans le fichier de sortie. Chaque fichier de sortie contient des données liées à une période spécifique appelée période de rotation. Tous les calculs de temps sont en GMT : Un jour commence à minuit GMT et se termine le lendemain à minuit GMT, même si les données écrites dans le fichier incluent un champ qui a été transformé en heure locale. </p> <p> Les valeurs disponibles sont les suivantes : </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> ANNÉE. Chaque fichier contient des données pour une année civile. </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MOIS. Chaque fichier contient des données pour un mois calendaire. Les mois sont numérotés de 1 (janvier) à 12 (décembre). </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> SEMAINE. Chaque fichier contient des données pour une semaine. Une semaine commence lundi. La semaine qui commence l’un des sept premiers jours de l’année est la semaine 1 et la semaine précédente (partielle), le cas échéant, est la semaine 0. </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> JOUR. Chaque fichier contient des données pour un jour calendaire. </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> HEURE. Chaque fichier contient des données pendant une heure. </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE. Aucune rotation n’est effectuée. Toutes les données sont écrites dans le même fichier (ou dans un ensemble de fichiers déterminé par d’autres paramètres). Voir le paramètre Format <span class="wintitle"> du nom de</span> fichier dans ce tableau. </li> 
      </ul> <p>La période de rotation par défaut des fichiers est JOUR. </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Définissez la rotation du fichier sur NONE uniquement lorsque vous travaillez en mode <span class="wintitle"></span>hors ligne. Voir la description du paramètre Mode <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> hors ligne</a> . </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Format du nom de fichier </td> 
      <td colname="col2"> <p>Facultatif. Format du nom du fichier de sortie. </p> <p> Chaque entrée de journal peut être stockée dans un fichier dont le nom est dérivé de l’heure de début de la période de rotation et éventuellement des valeurs des champs des lignes qu’elle contient. Les champs à utiliser dans le nom de fichier sont incorporés en tant qu’échappement de nom de champ (exprimé sous la forme %<i>fieldname</i>%). </p> <p>Les composants de nom de fichier associés à la période de rotation sont incorporés dans la chaîne de format à l’aide des séquences d’échappement suivantes : 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %aaaa% (année à quatre chiffres) </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (année à deux chiffres) </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (mois à deux chiffres, 01 - 12) </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww% (semaine à deux chiffres, 01 - 52) </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (jour à deux chiffres, 01 - 31) </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (heure à deux chiffres, 00 - 23) </li> 
      </ul> </p> <p> Le format de nom de fichier par défaut est <span class="filepath"> %yyy%%mm%%dd%-%x-mask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> Les séquences d’échappement sont sensibles à la casse. </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> Lorsque la valeur NONE est affectée à la période de rotation du fichier, une chaîne vide est remplacée pour chacune des séquences d’échappement, le cas échéant. </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> Une erreur est générée si <span class="wintitle"> le format</span> de nom de fichier n’entraîne pas un nom de fichier unique pour chaque période de rotation (voir le paramètre Période de rotation du fichier dans ce tableau). Par exemple, lors de l’utilisation de la période de rotation JOUR, les séquences d’échappement %dd%, %mm% et %yy% ou %yyy% doivent être présentes dans le modèle pour éviter la perte de données. </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> Si vous utilisez des séquences d’échappement de nom de champ dans le modèle et que le champ donné comporte de nombreuses valeurs distinctes, de nombreux fichiers de sortie sont écrits pour chaque période de rotation. Notez que ce scénario peut entraîner des performances médiocres. Vous devez donc utiliser cette fonctionnalité avec précaution. </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> Tous les calculs sont en GMT. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Exécuter au survol </td> 
      <td colname="col2"> <p>Facultatif. Lorsque chaque fichier est finalisé, une commande externe (Windows) peut être exécutée. La ligne de commande est dérivée du nom de fichier final en remplaçant les séquences d’échappement suivantes par ce paramètre : </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. Partie du répertoire du nom de fichier final, y compris la barre oblique inverse à la fin. </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. Nom de fichier (à l’exclusion du répertoire et de l’extension) du fichier final. </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. L’extension (y compris l’interligne ".") du nom de fichier final. </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %chemin d’accès%. Nom complet du chemin d’accès du fichier, équivalent à %dir%%file%%ext%. </li> 
      </ul> <p> Par défaut, ce paramètre est vide (aucune commande n’est exécutée). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Limite de mémoire </td> 
      <td colname="col2"> <p>Facultatif. Quantité de mémoire en octets utilisée pour mettre en mémoire tampon la sortie de l’exportateur. La valeur par défaut est de 10 000 000 octets. </p> <p> <p>Remarque :  Si de nombreux fichiers de sortie sont ouverts en même temps, vous pouvez augmenter cette valeur, mais vous pouvez réduire la quantité de mémoire disponible pour l’utilisation par d’autres composants du système. La diminution de cette valeur peut toutefois ralentir le processus d’exportation. Pour obtenir de l’aide, contactez Adobe. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Limite des fichiers ouverts </td> 
      <td colname="col2"> <p>Facultatif. Nombre maximal de fichiers pouvant être ouverts simultanément pour une sortie de l’exportateur. Si ce nombre est dépassé, une erreur est enregistrée dans le journal des événements et le serveur de l’outil de données s’arrête. La valeur par défaut est 1000. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Après avoir défini votre exportateur (et apporté des modifications à d’autres paramètres) dans le [!DNL Transform.cfg] fichier, enregistrez le fichier localement et enregistrez-le dans le profil approprié sur l’ordinateur du serveur de l’outil de données.
