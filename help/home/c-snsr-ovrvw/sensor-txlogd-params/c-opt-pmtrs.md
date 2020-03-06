---
description: Informations sur les paramètres facultatifs du fichier Sensor txlogd.conf.
solution: Insight
title: Paramètres facultatifs
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Optional Parameters{#optional-parameters}

Informations sur les paramètres facultatifs du fichier Sensor txlogd.conf.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>Permet de filtrer les adresses IP spécifiées. </p> <p>Lorsque vous filtrez une adresse particulière, un "paquet" n’est pas consigné. Cette fonctionnalité élimine les agents internes ou surveillés avant le traitement du journal, ce qui augmente la vitesse du traitement du journal et réduit les besoins en stockage des données. Vous pouvez utiliser des caractères génériques lors de la spécification des adresses. </p> <p>Exemple : <span class="filepath"> AddressFilter 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>Indiquez si vous souhaitez inclure ou exclure certains types de contenu de la journalisation. </p> <p>Les valeurs de paramètre sont associées au préfixe par rapport au type de contenu de la réponse. </p> <p>Par exemple, "image/" correspond à tous les types de contenu d’image, tandis que "image/gif" correspond exactement à ce type. Lorsque plusieurs correspondances se produisent pour un type de contenu donné, la correspondance la plus spécifique est utilisée. Par conséquent, vous pouvez placer "image/gif" dans le paramètre ContentFilterInclude et "image/" dans le paramètre ContentFilterExclude et les réponses "image/gif", mais tous les autres types d’image sont exclus. </p> <p>Exemple : <span class="filepath"> ContentFilterInclude *</span> </p> <p>Exemple : <span class="filepath"> ContentFilterExclure image/,texte/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Active la journalisation du débogage pour le module Web et l’émetteur. </p> <p>Utilisez ce paramètre lorsque le <span class="wintitle"> capteur</span> ne fonctionne pas correctement. Une fois ce paramètre défini, vous devez créer un fichier vide à l’emplacement spécifié du chemin d’accès et lui accorder des droits d’écriture pour tous les utilisateurs. Par exemple (dans un shell unix sur le serveur Web) : 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>Vous devez activer la journalisation du débogage pendant une courte période, après quoi le fichier journal doit être envoyé aux services de conseil Adobe pour analyse. </p> <p>Exemple : <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe recommande que ce paramètre soit d’abord défini dans un environnement de test afin de déterminer l’effet sur votre système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Désactive le champ spécifié </p> <p>Les utilisateurs peuvent éliminer les champs qu’ils n’utilisent pas ou qu’ils ne souhaitent pas stocker. Si le champ utilise des valeurs de chaîne, sa désactivation transmet une chaîne vide. Si le champ prend des valeurs numériques, sa désactivation transmet le nombre zéro (0). Vous pouvez désactiver les champs suivants : 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experience </li> 
     </ul> </p> <p>Exemple : <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Chemin d’accès au fichier de configuration de l’expérience contrôlée. </p> <p>Exemple : <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Ressource qui, lorsqu’elle est demandée, génère un nouvel ID de suivi et place l’utilisateur dans un groupe d’expériences. </p> <p> <p>Remarque :  Cette ressource n’a pas besoin d’exister physiquement sur le serveur Web. </p> </p> <p>Exemple : <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>Si vous souhaitez permettre à vos expériences contrôlées de remapper la totalité de votre site ou un sous-répertoire entier de votre site vers un autre emplacement, définissez ce paramètre sur "on". La valeur par défaut est "off". </p> <p>Exemple : <span class="filepath"> ExpPartialMatch désactivé</span> </p> <p> <p>Remarque :  Soyez très prudent lorsque vous définissez ce paramètre sur "on". </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Détermine si le premier clic de chaque nouvel utilisateur est consigné même si l’utilisateur demande un type de document qui est filtré par le paramètre ContentFilterExclude. </p> <p>La valeur par défaut est "no". </p> <p>En règle générale, les fichiers image sont exclus par le paramètre ContentFilterExclude. Si LogAllNewUsers est défini sur "yes" et que le tout premier document obtenu par un nouvel utilisateur à partir du serveur est une image, cette requête est enregistrée. Si le paramètre LogAllNewUsers est défini sur "no" ou non (et en supposant que les images sont filtrées par le paramètre ContentFilterExclure) et que le tout premier document qu’un nouvel utilisateur obtient du serveur est une image, cette demande n’est pas consignée. </p> <p>Exemple : <span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>durée, en secondes, pendant laquelle l’émetteur attend d’envoyer le prochain lot de paquets. </p> <p>La valeur par défaut est de 15. </p> <p>Exemple : <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Remarque :  Ne modifiez pas cette valeur de paramètre sans contacter préalablement Adobe Consulting Services. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Permet de désactiver le suivi des visiteurs, qui peut être utilisé pour se conformer aux stratégies d’exclusion. </p> <p>Lorsqu’il est activé, <span class="wintitle"> Sensor</span> ne consigne pas de "paquet" pour un visiteur dont le cookie V1st est défini sur l’ID de confidentialité spécifié. Aucune information n’étant consignée pour ces visiteurs, aucune information sur ces visiteurs n’est envoyée au serveur <span class="keyword"></span> de l’outil de données pour traitement. </p> <p>Pour activer cette fonctionnalité, procédez comme suit : 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID doit être défini avec la valeur 0 (zéro) dans le fichier <span class="filepath"> txlogd.conf</span> pour le <span class="wintitle"> capteur</span>. <p>Exemple : <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Les propriétaires de sites Web doivent écrire du code pour définir les cookies du visiteur (V1st) de sorte que la valeur de l’ID de cookie corresponde à la valeur de l’ID de confidentialité définie sur "<span class="filepath"> txlogd.conf</span>". </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Emplacement auquel l'émetteur (txlogd) envoie périodiquement des demandes pour voir si le site fonctionne correctement. </p> <p>Notez que l’emplacement est spécifié au format suivant, et non sous forme d’URL : </p> <p>http,<i>serverAddress,port,/resource</i> </p> <p>où <i>serverAddress</i> est le nom du serveur ou l’adresse IP, le <i>port</i> est le port d’écoute HTTP du serveur et <i>resource</i> est la ressource spécifique à demander (peut inclure une chaîne de requête). </p> <p>Vous pouvez spécifier plusieurs lignes SiteTest. </p> <p>Exemple : SiteTest <span class="filepath"> http,localhost,80,/test.html</span> </p> <p> <p>Remarque :  Seul http est actuellement pris en charge. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>Nom du cookie défini dans le navigateur du visiteur. </p> <p>La valeur par défaut est "v1st". </p> <p>Exemple : <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Indique si le serveur doit être validé par rapport au paramètre CertName. </p> <p>La valeur par défaut est "on". </p> <p>Exemple : <span class="filepath"> VerifyCertName sur</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Indique au <span class="wintitle"> capteur IIS</span> lequel des deux "hameoks" de journalisation possibles doit être utilisé pour journaliser un paquet </p> <p>Utilisez ce paramètre lorsque le <span class="wintitle"> capteur</span> IIS ne consigne pas correctement les paquets. Ce paramètre est défini sur "off" si le hook de journalisation par défaut ne fonctionnait pas correctement. La valeur par défaut est "on". </p> <p>Exemple : <span class="filepath"> IISCaptureBytesEnvoyé le</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Indique au <span class="wintitle"> capteur</span> lequel des deux crochets possibles doit être utilisé pour définir le cookie v1st. </p> <p>Utilisez ce paramètre lorsque le <span class="wintitle"> capteur</span> IIS ne définit pas correctement le cookie v1st. Ce paramètre serait défini sur "yes" si le crochet par défaut ne définissait pas correctement le cookie v1st. La valeur par défaut est "no". </p> <p>Exemple : <span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Par défaut, <span class="wintitle"> Sensor</span> envoie des en-têtes de réponse de contrôle du cache à chaque requête. Lorsque la fonction de contrôle du cache est activée, <span class="wintitle"> Sensor</span> envoie un en-tête Expire avec la valeur Thu, 01 Dec 1994 16:00:00 GMT au navigateur. </p> <p>Vous pouvez modifier les chaînes de réponse selon vos besoins en modifiant les deux lignes suivantes dans le fichier <span class="filepath"> txlogd.conf</span> : </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Exemple : </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Pour désactiver l'envoi des en-têtes de réponse de contrôle du cache, tapez un trait d'union pour chaque ligne comme illustré ci-dessous : </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dans ce paramètre... </th> 
   <th colname="col2" class="entry"> Spécifiez les... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Indique au <span class="wintitle"> capteur</span> lequel des deux crochets possibles doit être utilisé pour définir le cookie v1st. </p> <p>Vous utilisez ce paramètre lorsque Apache <span class="wintitle"> Sensor</span> ne définit pas correctement le cookie v1st. Ce paramètre serait défini sur "yes" si le crochet par défaut ne définissait pas correctement le cookie v1st. La valeur par défaut est "no". </p> <p>Exemple : <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseTwoHandlers </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Indique au <span class="wintitle"> capteur</span> de tenter de définir le cookie v1st dans les deux crochets. </p> <p>Vous utilisez ce paramètre lorsque Apache <span class="wintitle"> Sensor</span> ne définit pas correctement le cookie v1st. La valeur par défaut est "yes". </p> <p>Si la valeur est "yes" et que le cookie v1st n’est pas correctement défini dans le premier hook, le second est utilisé. Si la valeur est "no", vous devez définir le paramètre ApacheUseAlternateHandler pour indiquer quel hook utiliser pour définir le cookie v1st. </p> <p>Exemple : <span class="filepath"> ApacheUseTwoHandlers oui</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Par défaut, <span class="wintitle"> Sensor</span> envoie des en-têtes de réponse de contrôle du cache à chaque requête. Lorsque la fonction de contrôle du cache est activée, <span class="wintitle"> Sensor</span> envoie un en-tête Expire avec la valeur Thu, 01 Dec 1994 16:00:00 GMT au navigateur. </p> <p>Vous pouvez modifier les chaînes de réponse selon vos besoins en modifiant les deux lignes suivantes dans le fichier <span class="filepath"> txlogd.conf</span> : </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Exemple : </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Pour désactiver l'envoi des en-têtes de réponse de contrôle du cache, tapez un trait d'union pour chaque ligne comme illustré ci-dessous : </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Remarque :  Adobe recommande de ne pas désactiver cette fonctionnalité. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dans ce paramètre... </th> 
   <th colname="col2" class="entry"> Spécifiez les... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Indique au <span class="wintitle"> capteur</span> lequel des deux crochets possibles doit être utilisé pour définir le cookie v1st. </p> <p>Vous utilisez ce paramètre lorsque Apache <span class="wintitle"> Sensor</span> ne définit pas correctement le cookie v1st. Ce paramètre serait défini sur "yes" si le crochet par défaut ne définissait pas correctement le cookie v1st. La valeur par défaut est "no". </p> <p>Exemple : <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseTwoHandlers </td> 
   <td colname="col2"> <p>Définissez ce paramètre uniquement lorsque vous travaillez avec Adobe Consulting Services. </p> <p>Indique au <span class="wintitle"> capteur</span> de tenter de définir le cookie v1st dans les deux crochets. </p> <p>Vous utilisez ce paramètre lorsque Apache <span class="wintitle"> Sensor</span> ne définit pas correctement le cookie v1st. La valeur par défaut est "yes". </p> <p>Si la valeur est "yes" et que le cookie v1st n’est pas correctement défini dans le premier hook, le second est utilisé. Si la valeur est "no", vous devez définir le paramètre ApacheUseAlternateHandler pour indiquer quel hook utiliser pour définir le cookie v1st. </p> <p>Exemple : <span class="filepath"> ApacheUseTwoHandlers oui</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

