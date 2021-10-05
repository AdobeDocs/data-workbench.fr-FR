---
description: Après avoir installé les fichiers de programme Insight, vous devez télécharger et installer le certificat numérique fourni par Adobe.
title: Téléchargement et installation du certificat numérique
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
exl-id: 0dff95ae-880b-45d5-96df-4eb6bea58891
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '2743'
ht-degree: 39%

---

# Téléchargement et installation du certificat numérique{#downloading-and-installing-the-digital-certificate}

Après avoir installé les fichiers de programme Insight, vous devez télécharger et installer le certificat numérique fourni par Adobe.

## Téléchargement et installation du certificat numérique {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Après avoir installé les fichiers de programme Insight, vous devez télécharger et installer le certificat numérique fourni par Adobe.

## Compréhension des certificats numériques {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe utilise des certificats numériques au format X.509 pour identifier et authentifier les composants de client et de serveur qui constituent une implémentation.

<!--
c_undst_dgtl_crtf.xml
-->

Lorsque vous installez Insight, vous devez installer le certificat numérique qui autorise une personne nommée (Jane Smith, par exemple) à utiliser l’application client installée.

>[!NOTE]
>
>Si vous devez migrer Insight vers un autre ordinateur ou un autre utilisateur nommé, vous devez obtenir un nouveau certificat auprès d’Adobe. Pour ce faire, contactez le service clientèle d’Adobe.

Insight présente ce certificat numérique pour accéder à un composant de serveur. Un administrateur d’un composant de serveur peut restreindre l’accès aux ressources du serveur en fonction du nom commun ou des valeurs des entités organisationnelles qui apparaissent dans le certificat de l’utilisateur.

Les certificats numériques X.509 installés avec des applications Adobe permettent également à ses composants de client et de serveur d’échanger des informations par le biais du protocole SSL (Secure Sockets Layer). Le protocole SSL sécurise les transmissions par HTTP à l’aide d’un système de cryptage de clé public et privé. La mise en œuvre du protocole SSL par Adobe prend en charge les clés RSA 1 024 bits et utilise un algorithme de chiffrement RC4 128 bits.

Outre la sécurité, le certificat numérique que vous installez fonctionne également comme une clé de licence qui vous permet d’exécuter Insight. Pour fonctionner correctement, un certificat numérique doit être fixe et en cours, sinon l’application ne démarre pas.

## Certificats fixes {#section-984aa8f2f5a1448cadc4afea978aedc9}

Un certificat fixe est un certificat numérique qui a été enregistré sur l’ordinateur sur lequel il est installé. Le verrouillage de noeud associe de manière permanente un certificat à un identifiant de noeud spécifique (une valeur qui identifie de manière unique un ordinateur particulier). Pour verrouiller votre certificat, votre ordinateur doit disposer d’un accès Internet au serveur de licences d’Adobe ou à un serveur proxy ayant accès au serveur de licences.

Si vous effectuez l’installation sur un ordinateur qui ne peut pas accéder à Internet, vous devez obtenir et installer un certificat préverrouillé spécial, comme décrit dans la section [Utilisation de certificats numériques sur des ordinateurs sans accès à Internet](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1).

Si vous effectuez l’installation sur un ordinateur qui peut accéder à Internet, votre certificat numérique sera automatiquement verrouillé lors du premier démarrage d’Insight. Une fois le noeud verrouillé, le certificat ne peut pas être utilisé sur un autre ordinateur. Si vous devez migrer Insight vers un autre ordinateur, vous devez obtenir un nouveau certificat déverrouillé de Adobe.

## Certificats en cours {#section-0816b031df3e415ab3f0205b720c723e}

En plus d’être déverrouillé, votre certificat numérique doit être à jour. Pour rester en cours, votre certificat doit être régulièrement revalidé (en général tous les 30 jours, mais cette durée peut varier selon l’accord passé avec Adobe). Si votre ordinateur dispose d’un accès Internet, le processus de revalidation est complètement transparent. Insight se connecte automatiquement au serveur de licences et revalide le certificat si nécessaire. Si votre ordinateur ne dispose pas d’un accès Internet, vous devez installer manuellement un certificat mis à jour, comme décrit dans la section suivante.

## Utilisation de certificats numériques sur des ordinateurs sans accès à Internet {#section-d3c060131d7f45cda27f68848b704fa1}

Si vous effectuez l’installation sur un ordinateur qui ne peut pas accéder à Internet, vous devez demander un certificat préverrouillé pour votre installation d’Insight. Un certificat préverrouillé est un certificat numérique qui, par Adobe, se verrouille manuellement sur l’identifiant de noeud de l’ordinateur.

Pour demander un certificat préverrouillé, vous devez envoyer l’identifiant de noeud et votre numéro de certificat à l’assistance clientèle Adobe. Pour obtenir l’identifiant de noeud de votre ordinateur, contactez l’Assistance clientèle d’Adobe pour demander l’utilitaire [!DNL Node Identifier] d’Adobe. Vous pouvez également obtenir l’identifiant de noeud à partir de l’alerte émise par Insight lorsqu’il tente de se connecter au serveur de licences et ne peut pas le faire. Lorsque vous recevez le certificat préverrouillé, installez-le comme décrit dans les deux dernières étapes de la section [Installation des certificats numériques](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38).

Lorsque le certificat doit être revalidé, vous devez télécharger un nouveau certificat validé à partir du serveur de licences et le réinstaller sur votre ordinateur (sauf si votre accord avec des états Adobes le prévoit).

## Installation de certificats numériques {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Télécharger et installer le certificat numérique**

1. Ouvrez votre navigateur Web à [!DNL https:\\license.visualsciences.com].

   >[!NOTE]
   >
   >À ce stade, votre navigateur peut vous inviter à présenter un certificat numérique. Si tel est le cas, cliquez sur **[!UICONTROL Cancel]** pour fermer la boîte de dialogue.

1. Sur l’écran de connexion, saisissez l’[!DNL Account Name] et le [!DNL Password] que vous envoyés par Adobe, puis cliquez sur **[!UICONTROL login]**.
1. Recherchez le certificat émis pour votre instance d’Insight ( *Votre nom*.pem) et cliquez sur l’icône ![](assets/btn_save_certificatedownload.PNG) associée à ce certificat.
1. Lorsque vous êtes invité à enregistrer le certificat, cliquez sur **[!UICONTROL Save]**.
1. Téléchargez le fichier dans le dossier [!DNL Certificates] du répertoire où vous avez installé Insight.

   Ce dossier contient un fichier de certificat nommé [!DNL trust_ca_cert.pem]. Les deux fichiers de certificat doivent toujours être présents pour qu’Insight fonctionne.

## Boutique de certificats Windows {#concept-4acb13b7de9340ea8cde8ad84b93358d}

La boutique de certificats Windows vous permet de stocker le certificat et la clé privée du client pour la communication SSL avec les serveurs.

<!--
crypto-api.xml
-->

La boutique de certificats Windows destinée au client constitue une nouvelle fonctionnalité qui vous permet de stocker le certificat de communication SSL ainsi que la clé privée dans la boutique de certificats Windows plutôt que dans un fichier `Insight/Certificates/<CertName>.pem`. Il peut être préférable d’utiliser la boutique de certificats Windows si vous utilisez la boutique de certificats pour d’autres applications et souhaitez gérer tous les certificats à un seul endroit. La boutique de certificats peut aussi être utile aux utilisateurs qui apprécient la journalisation d’audit Windows complémentaire qu’elle fournit.

>[!NOTE]
>
>L’obtention de licences avec le serveur de licences est toujours possible à l’aide du fichier `<Common Name>.pem` existant, et le certificat obtenu à partir de la boutique de certificats sera uniquement utilisé à des fins de communication avec les serveurs que vous précisez.

## Conditions préalables {#section-69b18600052145ff8e5299b7123e69c5}

1. Vous devez avoir accès au fichier [!DNL certmgr.msc] avec possibilité d’importer un certificat et une clé dans la boutique **personnelle**. (La plupart des utilisateurs Windows devraient remplir par défaut ces conditions.)

1. L’utilisateur qui effectue la configuration doit disposer d’une copie de l’outil de ligne de commande **OpenSSL**.
1. Le serveur et le client doivent déjà être configurés pour utiliser un certificat SSL personnalisé, ce qui explique comment stocker le certificat client dans la boutique de certificats Windows plutôt que de le stocker dans le répertoire **Certificats**.

## Configuration de la boutique de certificats Windows {#section-3629802122e947d4b4f63e8b732cfe27}

La boutique de certificats Windows pour les clients est activée de la manière suivante :

**Étape 1 : importez le certificat SSL et la clé privée de l’utilisateur dans la boutique de certificats Windows.**

Dans [Utilisation de certificats personnalisés en Data Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) , vous êtes invité à placer le certificat et la clé SSL dans le répertoire suivant :

```
<
<filepath>
  DWB Install folder
</filepath>>\Certificates\
```

Le nom du certificat est `<Common Name>.pem`, tel qu’Analytics Server 1.pem (et non le fichier trust_ca_cert.pem).

Avant que le certificat et la clé privée puissent être importés, ils doivent être convertis depuis un format .[!DNL pem] vers un format [!DNL .pfx], par exemple [!DNL pkcs12.pfx]).

1. Ouvrez une invite de commandes ou un terminal et accédez au répertoire :

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Exécutez [!DNL openssl] avec les arguments suivants (avec le véritable nom du fichier [!DNL .pem]) :

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Si vous y êtes invité, appuyez sur **Entrée** pour ignorer la saisie d’un mot de passe d’exportation.

1. Exécutez [!DNL certmgr.msc] depuis l’invite d’exécution, le menu de démarrage ou la ligne de commande.
1. Ouvrez la boutique **personnelle** de certificats pour l’utilisateur actuel.

   ![](assets/6_5_crypto_api_0.png)

1. Cliquez avec le bouton droit de la souris sur **Certificats**, puis sur **Toutes les tâches** > **Importer**.

   Assurez-vous que l’option **Utilisateur actuel** est sélectionnée, puis cliquez sur **Suivant**.

   ![](assets/6_5_crypto_api_4.png)

1. Cliquez sur **Parcourir** et sélectionnez le fichier `<CommonName>.pfx` que vous avez créé précédemment. Vous devrez modifier l’extension du fichier dans la liste déroulante, et passer d’un certificat X.509 à un format **Personal Information Exchange** ou **Tous les fichiers** pour pouvoir l’afficher.

   Sélectionnez le fichier et cliquez sur **Ouvrir**, puis sur **Suivant**.

1. Ne saisissez pas de mot de passe et assurez-vous que seules les options **Marquer cette clé comme exportable** et **Inclure toutes les propriétés étendues** sont sélectionnées.

   ![](assets/6_5_crypto_api_3.png)

   Cliquez sur **Suivant**.

1. Assurez-vous que l’option **Placer tous les certificats dans la boutique ci-contre** est sélectionnée et que la boutique de certificats répertoriée est bien la boutique **personnelle**. (Si vous êtes un utilisateur avancé, vous pouvez sélectionner une autre boutique à ce stade, mais vous devrez plus tard modifier la configuration.)

1. Cliquez sur **Suivant**, puis sur **Terminer**. Une boîte de dialogue s’affiche pour vous indiquer que l’importation a réussi et que vous pouvez voir votre certificat dans le dossier Certificats de la boutique.

   >[!NOTE]
   >
   >Examinez attentivement les champs **Émis vers** et **Émis par**. Ils sont nécessaires pour mener à bien l’étape suivante.

**Étape 2 : modifiez le fichier Insight.cfg.**

Le fichier [!DNL Insight.cfg] doit être modifié pour commander à Data Workbench d’utiliser la fonctionnalité Boutique de certificats Windows. Certains paramètres supplémentaires doivent être renseignés pour chaque entrée de serveur dans ce fichier. Si ces paramètres sont omis, le poste de travail opte par défaut pour la configuration de certificat existante. Si ces paramètres sont renseignés avec des valeurs incorrectes, le poste de travail passe en état d’erreur et vous devrez vous reporter au fichier journal pour obtenir des informations sur l’erreur.

1. Ouvrez le fichier **Insight.cfg** (situé dans le répertoire d’installation **Insight**).

1. Faites défiler l’écran vers le bas jusqu’à l’entrée de serveur que vous souhaitez configurer. Si vous souhaitez utiliser la boutique de certificats Windows pour chaque serveur, vous devez modifier chaque entrée du vecteur d’objets [!DNL serverInfo].
1. Ajoutez ces paramètres à leur fichier [!DNL Insight.cfg]. Vous pouvez réaliser cette opération à partir du poste de travail ou manuellement en ajoutant les paramètres suivants à l’objet [!DNL serverInfo]. (Assurez-vous d’utiliser des espaces et non pas des caractères de tabulation, et évitez toute erreur typographique ou de syntaxe dans ce fichier. )

   ```
   SSL Use CryptoAPI = bool: true
   SSL CryptoAPI Cert Name = string: <Common Name>
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC
   SSL CryptoAPI Cert Store Name = string: My
   ```

   Le booléen active ou désactive la fonctionnalité. Le nom du certificat correspond à la valeur du champ **Émetteur vers** dans le gestionnaire de certificats. Le nom de l’émetteur du certificat correspond à la valeur du champ **Émis par**, et le **Nom de la boutique** doit correspondre au nom de la boutique de certificats.

   >[!NOTE]
   >
   >Le nom « Personnelle » dans le Gestionnaire de certificats (certmgr.msc) fait bien référence à la boutique de certificats appelée **Ma.** Par conséquent, si vous importez votre clé et votre certificat de communication SSL (.PFX) dans la boutique de certificats **personnelle** comme recommandé, vous devez définir la chaîne **Nom de la boutique de certificats SSL CryptoAPI** sur « Ma ». Si vous définissez ce paramètre sur « Personnelle », l’opération échouera. Il s’agit d’une particularité de la boutique de certificats Windows.

   Vous pouvez obtenir une liste complète des boutiques prédéfinies du système à cette adresse : [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Il est possible que votre système dispose de boutiques de certificats supplémentaires. Si vous souhaitez utiliser une boutique autre que la boutique « Personnelle » (comme **Ma**), vous devez obtenir le nom canonique de la boutique de certificats et le renseigner dans le fichier [!DNL Insight.cfg]. (La documentation Windows fait aussi bien référence au nom de la boutique du système comme « Ma » que comme « MA ». Le respect de la casse ne semble pas être nécessaire pour ce paramètre.)

1. Après avoir ajouté ces paramètres et vérifié que les valeurs correspondent à la liste du Gestionnaire de certificats Windows, enregistrez le fichier [!DNL Insight.cfg].

Vous pouvez maintenant démarrer le poste de travail (ou vous déconnecter/reconnecter au serveur). Data Workbench devrait charger votre certificat et votre clé depuis la boutique de certificats et se connecter normalement.

## Sortie de journal {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Lorsqu’un certificat est introuvable ou invalide, ce message d’erreur est envoyé au fichier [!DNL HTTP.log].

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>La structure de journalisation L4 peut être activée en configurant le fichier [!DNL L4.cfg] (consultez votre gestionnaire de compte pour réaliser cette configuration).

## Utilisation de certificats personnalisés dans Data Workbench {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Instructions pour l’utilisation de certificats personnalisés.

<!--
using-custom-certificates-DWB.xml
-->

Un certificat utilisé par le client ou le serveur du Data Workbench doit être signé par une autorité de certification approuvée. Les clients Data Workbench reçoivent des certificats signés par l’autorité de certification Visual Sciences. Ces certificats sont approuvés par le logiciel du Data Workbench, puisque le [!DNL trust_ca_cert.pem] (fourni avec le logiciel Insight et stocké dans le répertoire **Certificats** des serveurs et des clients) contient un *certificat d’autorité de certification racine* pour l’autorité de certification Visual Sciences. Ces certificats sont utilisés à la fois pour la licence du logiciel et pour l’authentification lorsque les clients et les serveurs communiquent entre eux à l’aide du protocole SSL. Seuls les certificats émis par l’autorité de certification Visual Sciences peuvent être utilisés pour les licences, mais d’autres certificats peuvent être utilisés pour la communication et l’authentification. Les certificats délivrés par des autorités de certification autres que Visual Sciences sont appelés *certificats personnalisés.*

**Remarque importante :** pour les serveurs et les clients, les logiciels Data Workbench utilisent les fichiers de certificat installés dans le  **** répertoire de certificats du client ou du serveur, ou les certificats explicitement identifiés dans sa configuration. Cependant, vous pouvez également utiliser la boutique de certificats Windows pour les clients.

Les instructions suivantes décrivent les procédures à suivre pour utiliser des certificats personnalisés pour la communication entre les clients et les serveurs de Data Workbench. Tous les détails ne sont pas une exigence difficile et différentes variantes du processus peuvent être utilisées. Toutefois, les procédures ci-dessous ont été testées pour fonctionner.

## Configuration de certificats client personnalisés {#section-2083fd41973e451fa404e7a4ae4da591}

1. Ajoutez le certificat de l’autorité de certification émettrice à la [!DNL trust_cert_ca.pem], qui est installée dans le répertoire **Certificats** du client et de chaque serveur de chaque grappe à laquelle vous pouvez accéder à l’aide de ce certificat personnalisé.

1. Obtenez un certificat personnalisé pour chaque serveur de la grappe avec les conditions suivantes :

   1. Le certificat est formaté en tant que certificat [!DNL .pem].
   1. Le certificat contient sa clé et n’est pas chiffré (c’est-à-dire qu’il ne comporte pas de mot de passe/expression de passe).

      Un certificat contient sa clé avec l’une des lignes suivantes :

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Une méthode pour supprimer l’expression de mot de passe d’un certificat [!DNL .pem] :

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat a le CN, l&#39;O, l&#39;OU, etc. comme requis pour ce client dans le fichier [!DNL Access Control.cfg] des serveurs.
   1. Le certificat a été délivré avec un ***** *client* (ou *serveur* **et** *client*).

      Pour vérifier qu’un certificat comporte un code d’objectif de serveur et/ou de client, les commandes suivantes peuvent être utilisées :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour les certificats de serveur, les deux commandes doivent générer :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande est requise pour obtenir [!DNL OK].

1. Placez le certificat dans le répertoire **Certificats** du client.
1. Dans [!DNL Insight.cfg] sous *serverInfo* pour chaque grappe que vous souhaitez utiliser ce certificat, assurez-vous que le *certificat client personnalisé* est nommé, par exemple :

   ```
   Servers = vector: 1 items
     0 = serverInfo:
       SSL Client Certificate = string:
     <my_custom_client_cert.pem>
   ```

## Configuration de certificats de serveur personnalisés {#setting-up-custom-server-certificates}

Cette section suppose que vous disposez d’une grappe en cours d’exécution, utilisant des certificats émis par Visual Sciences, et que la configuration suit les pratiques courantes (telles que le répertoire *Composants pour les serveurs de traitement* sur le maître est synchronisé avec les répertoires *Composants* de tous les DPU).

1. Ajoutez le certificat de l’autorité de certification émettrice à la [!DNL trust_cert_ca.pem] installée sur chaque serveur de la grappe et chaque client qui doit communiquer avec cette grappe.
1. Obtenez un certificat personnalisé pour chaque serveur de la grappe en respectant les exigences suivantes :

   1. Le certificat personnalisé est formaté en tant que certificat [!DNL .pem].
   1. Le certificat contient sa clé et n’est pas chiffré (c’est-à-dire qu’il ne comporte pas de mot de passe/expression de passe).

      Un certificat contient sa clé s’il comporte une ligne du type :

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Une méthode pour supprimer l’expression de mot de passe d’un certificat [!DNL .pem] :

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat possède le même CN que le [!DNL server_cert.pem] actuellement installé sur le serveur.
   1. Le certificat a été délivré dans le but *server* et *client*.

      Pour vérifier qu’un certificat comporte un code d’objectif de serveur et/ou de client, les commandes suivantes peuvent être utilisées :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour les certificats de serveur, les deux commandes doivent générer :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande est requise pour obtenir [!DNL OK].

1. Installez le certificat personnalisé de chaque serveur dans le répertoire **Certificats** du serveur sous la forme [!DNL custom_communications_cert.pem].

1. Dans un éditeur de texte, ajoutez la ligne suivante au fichier **Communications.cfg** dans les répertoires *Composants* et *Composants pour les serveurs de traitement*, directement sous la première ligne ( [!DNL component = CommServer]) :

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Redémarrez tous les serveurs.

**À propos de l’avertissement d’échec de certificat**

Lorsque le serveur ou le client Insight recherche un certificat **license** dans le répertoire **Certificats**, il tente de valider tous les certificats (à l’exception de [!DNL trust_ca_cert.pem]) par rapport à une copie codée en dur du certificat de l’autorité de certification Insight, qui échoue sur tout certificat personnalisé présent dans le répertoire. Le serveur émet cet avertissement :

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Cet avertissement peut être ignoré en toute sécurité.

## Chiffrement de chaîne {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Chiffrez les mots de passe et autres chaînes lors de la communication entre le client et le serveur.

<!--
string_encryption.xml
-->

Lors de la communication entre le client Data Workbench (poste de travail) et le serveur, vous pouvez enregistrer un paramètre Value (par exemple un mot de passe) avec le type *EncryptedString*. Le paramètre est masqué et la chaîne est enregistrée dans la *boutique d’informations d’identification Windows* sur le serveur avec la clé correspondante renvoyée. Il stocke principalement les informations d’identification utilisées dans les exportations, mais peut être utilisé pour chiffrer n’importe quel paramètre.

* Un nouveau dossier a été ajouté sur Server\**EncryptStrings**.

   C’est là que vous définissez le fichier de configuration pour chiffrer les chaînes.

* Un nouveau fichier de configuration a été ajouté à l’adresse Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Ce fichier interroge le dossier *Server*\*EncryptStrings* pour les fichiers de configuration de chiffrement.

**Pour chiffrer une chaîne** :

1. Créez un fichier de configuration **EncryptedStrings.cfg** pour une chaîne avec les champs suivants définis :

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier
     Value = string: // Value to be encrypted
   ```

   * *Valeur*  : ce champ contient la chaîne de texte brut qui doit être chiffrée.

      Il s’agit uniquement d’un chiffrement côté serveur. Le paramètre *Valeur* est chiffré uniquement sur l’ordinateur serveur.

   * *Nom*  : ce champ contient une valeur qui identifie la chaîne chiffrée.
   * *EncryptValue*  : ce champ reste vide dans le fichier de configuration d’entrée. La valeur cryptée sera renvoyée dans ce champ.

   Vous pouvez ajouter plusieurs valeurs **NameEncryptValuePair** pour différents champs de chiffrement.

   >[!NOTE]
   >
   >Tous les champs Valeur vides seront supprimés.

1. Enregistrez le fichier **EncryptedStrings.cfg** dans le dossier Server\**EncryptStrings**.

**Fichier de sortie**

Un fichier de sortie sera généré avec le même nom que le fichier d’entrée avec un nom &quot;a0/>filename *.*** encryptedextension. Par exemple, si le fichier d’entrée est nommé *sample.cfg*, le fichier de sortie sera nommé *sample.cfg.encrypted*.
