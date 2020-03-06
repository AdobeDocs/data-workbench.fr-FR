---
description: Après avoir installé les fichiers du programme Insight, vous devez télécharger et installer le certificat numérique fourni par Adobe.
title: Téléchargement et installation du certificat numérique
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Téléchargement et installation du certificat numérique{#downloading-and-installing-the-digital-certificate}

Après avoir installé les fichiers du programme Insight, vous devez télécharger et installer le certificat numérique fourni par Adobe.

## Téléchargement et installation du certificat numérique {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Après avoir installé les fichiers du programme Insight, vous devez télécharger et installer le certificat numérique fourni par Adobe.

## Présentation des certificats numériques {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe utilise des certificats numériques X.509 pour identifier et authentifier les composants client et serveur qui constituent une implémentation.

<!--
c_undst_dgtl_crtf.xml
-->

Lorsque vous installez Insight, vous devez installer le certificat numérique qui autorise une personne nommée (par exemple, Jane Smith) à utiliser l’application cliente installée.

>[!NOTE]
>
>Si vous devez migrer Insight vers un autre ordinateur ou un autre utilisateur nommé, vous devez obtenir un nouveau certificat d’Adobe. Pour ce faire, contactez le service à la clientèle d’Adobe.

Insight présente ce certificat numérique pour accéder à un composant serveur. Un administrateur d’un composant serveur peut restreindre l’accès aux ressources du serveur en fonction du nom commun ou des valeurs d’unité d’organisation qui apparaissent dans le certificat de l’utilisateur.

Les certificats numériques X.509 installés avec les applications Adobe permettent également à ses composants client et serveur d’échanger des informations via SSL (Secure Sockets Layer). SSL sécurise les transmissions via HTTP à l’aide d’un système de chiffrement de clé publique et privée. L’implémentation de SSL par Adobe prend en charge les clés RSA 1 024 bits et utilise un algorithme de chiffrement RC4 128 bits.

Outre la sécurité, le certificat numérique que vous installez fonctionne également comme une clé de licence qui vous permet d’exécuter Insight. Pour fonctionner correctement, un certificat numérique doit être verrouillé par un noeud et à jour, sinon l’application ne démarre pas.

## Certificats verrouillés sur le noeud {#section-984aa8f2f5a1448cadc4afea978aedc9}

Un certificat verrouillé par un noeud est un certificat numérique qui a été enregistré sur l’ordinateur sur lequel il est installé. Le verrouillage de noeud associe de manière permanente un certificat à un identifiant de noeud spécifique (une valeur qui identifie de manière unique un ordinateur particulier). Pour verrouiller votre certificat par un noeud, votre ordinateur doit disposer d’un accès Internet au serveur Adobe License Server ou à un serveur proxy qui a accès au serveur License Server.

Si vous effectuez l’installation sur un ordinateur qui ne peut pas accéder à Internet, vous devez obtenir et installer un certificat préverrouillé spécial, comme décrit dans [Utilisation de certificats numériques sur des ordinateurs sans accès](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1)à Internet.

Si vous effectuez l’installation sur un ordinateur qui peut accéder à Internet, votre certificat numérique sera verrouillé automatiquement lors du premier démarrage d’Insight. Une fois le certificat verrouillé sur un noeud, il ne peut plus être utilisé sur un autre ordinateur. Si vous devez migrer Insight vers un autre ordinateur, vous devez obtenir un nouveau certificat déverrouillé d’Adobe.

## Certificats actuels {#section-0816b031df3e415ab3f0205b720c723e}

Outre le fait d’être verrouillé sur un noeud, votre certificat numérique doit être à jour. Pour rester à jour, votre certificat doit être régulièrement revalidé (généralement tous les 30 jours, mais peut varier selon votre accord avec Adobe). Si votre ordinateur a accès à Internet, le processus de revalidation est complètement transparent. Insight se connecte automatiquement au serveur de licences et revalide le certificat si nécessaire. Si votre ordinateur ne dispose pas d’un accès Internet, vous devez installer manuellement un certificat mis à jour, comme décrit dans la section suivante.

## Utilisation de certificats numériques sur des ordinateurs sans accès à Internet {#section-d3c060131d7f45cda27f68848b704fa1}

Si vous effectuez l’installation sur un ordinateur qui ne peut pas accéder à Internet, vous devez demander un certificat pré-verrouillé pour votre installation d’Insight. Un certificat pré-verrouillé est un certificat numérique qu’Adobe verrouille manuellement sur l’identifiant de noeud de l’ordinateur.

Pour demander un certificat pré-verrouillé, vous devez envoyer l’identifiant de noeud et le numéro de votre certificat au service à la clientèle Adobe. Pour obtenir l’identifiant de noeud pour votre ordinateur, contactez le service à la clientèle d’Adobe pour demander l’utilitaire Adobe [!DNL Node Identifier] . Vous pouvez également obtenir l’identifiant de noeud à partir de l’alerte qu’Insight génère lorsqu’il tente de se connecter au serveur de licences et ne peut pas le faire. Lorsque vous recevez le certificat préverrouillé, installez-le comme décrit dans les deux dernières étapes de [l’installation des certificats](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38)numériques.

Lorsque le certificat doit être revalidé, vous devez télécharger un nouveau certificat validé à partir du serveur de licences et le réinstaller sur votre ordinateur (à moins que votre accord avec Adobe n’indique le contraire).

## Installation des certificats numériques {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Pour télécharger et installer le certificat numérique**

1. Ouvrez votre navigateur Web pour [!DNL http:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Votre navigateur peut vous inviter à présenter un certificat numérique à ce stade. Si tel est le cas, cliquez **[!UICONTROL Cancel]** pour fermer la boîte de dialogue.

1. Dans l’écran de connexion, saisissez le [!DNL Account Name] et le nom [!DNL Password] que vous avez reçus d’Adobe, puis cliquez sur **[!UICONTROL login]**.
1. Recherchez le certificat qui a été émis pour votre instance d’Insight ( *Votre nom*.pem) et cliquez sur l’ ![](assets/btn_save_certificatedownload.PNG) icône associée à ce certificat.
1. Lorsque vous êtes invité à enregistrer le certificat, cliquez sur **[!UICONTROL Save]**.
1. Téléchargez le fichier dans le [!DNL Certificates] dossier du répertoire dans lequel vous avez installé Insight.

   Ce dossier contient un fichier de certificat nommé [!DNL trust_ca_cert.pem]. Les deux fichiers de certificat doivent toujours être présents pour que Insight fonctionne.

## Magasin de certificats Windows {#concept-4acb13b7de9340ea8cde8ad84b93358d}

Le magasin de certificats Windows ne permet pas de stocker le certificat du client et sa clé privée dans le magasin de certificats Windows pour la communication SSL avec les serveurs.

<!--
crypto-api.xml
-->

Le magasin de certificats Windows pour le client est une nouvelle fonctionnalité qui vous permet de stocker le certificat de communication SSL et la clé privée dans le magasin de certificats Windows plutôt que dans un `Insight/Certificates/<CertName>.pem` fichier. Il peut être préférable d’utiliser le magasin de certificats Windows si vous utilisez le magasin de certificats pour d’autres applications et souhaitez gérer les certificats au même endroit, ou pour les utilisateurs qui bénéficient de la journalisation d’audit Windows supplémentaire fournie par le magasin de certificats Windows.

>[!NOTE]
>
>Les licences avec le serveur de licences sont toujours conservées à l’aide du `<Common Name>.pem` fichier existant et le certificat obtenu à partir du magasin de certificats ne sera utilisé que pour la communication aux serveurs que vous spécifiez.

## Conditions préalables {#section-69b18600052145ff8e5299b7123e69c5}

1. Vous devez avoir accès au [!DNL certmgr.msc] fichier avec la possibilité d’importer un certificat et une clé dans le magasin **personnel** . (Cela doit être vrai par défaut pour la plupart des utilisateurs de Windows.)

1. L’utilisateur effectuant la configuration doit disposer d’une copie de l’outil de ligne de commande **OpenSSL** .
1. Le serveur et le client doivent déjà être configurés pour utiliser un certificat SSL personnalisé, en donnant des instructions pour stocker le certificat client dans le magasin de certificats Windows au lieu de le stocker dans le répertoire **Certificats** .

## Configuration du magasin de certificats Windows {#section-3629802122e947d4b4f63e8b732cfe27}

Le magasin de certificats Windows pour les clients est activé en procédant comme suit :

**Étape 1 : Importez le certificat SSL et la clé privée de l’utilisateur dans le magasin de certificats Windows.**

Dans [Utilisation de certificats personnalisés dans les outils](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) de données, vous êtes invité à placer le certificat et la clé SSL dans le répertoire suivant :

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Le nom du certificat est `<Common Name>.pem` tel qu’Analytics Server 1.pem (et non le fichier trust_ca_cert.pem).

Avant de pouvoir importer le certificat et la clé privée, ils doivent être convertis à partir de . [!DNL pem] dans un [!DNL .pfx] format, par exemple [!DNL pkcs12.pfx] ).

1. Ouvrez une invite de commande ou un terminal et accédez au répertoire :

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Exécutez [!DNL openssl] avec les arguments suivants (avec le nom [!DNL .pem] de fichier réel) :

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Si vous y êtes invité, appuyez sur **Entrée** pour ignorer la saisie d’un mot de passe d’exportation.

1. Exécutez [!DNL certmgr.msc] à partir de l’invite d’exécution, du menu de démarrage ou de la ligne de commande.
1. Ouvrez le magasin de certificats **personnels** pour l’utilisateur actuel.

   ![](assets/6_5_crypto_api_0.png)

1. Cliquez avec le bouton droit de la souris sur **Certificats** et cliquez sur **Toutes les tâches** > **Importer**.

   Assurez-vous que l’option Utilisateur **** actuel est sélectionnée, puis cliquez sur **Suivant**.

   ![](assets/6_5_crypto_api_4.png)

1. Cliquez sur **Parcourir** et sélectionnez le `<CommonName>.pfx` fichier que vous avez créé précédemment. Vous devrez changer la liste déroulante des extensions de fichier d&#39;un certificat X.509 à un échange **de renseignements** personnels ou à **tous les fichiers** pour pouvoir le voir.

   Sélectionnez le fichier, cliquez sur **Ouvrir**, puis sur **Suivant**.

1. N’entrez pas de mot de passe et assurez-vous que seules les options **Marquer cette clé comme exportable** et **Inclure toutes les propriétés** étendues sont sélectionnées.

   ![](assets/6_5_crypto_api_3.png)

   Cliquez sur **Suivant**.

1. Assurez-vous que l’option **Placer tous les certificats dans le magasin** suivant est sélectionnée et que le magasin de certificats répertorié est **Personnel**. (Si vous êtes un utilisateur avancé, vous pouvez sélectionner un autre magasin à ce stade, mais vous devrez modifier la configuration ultérieurement.)

1. Cliquez sur **Suivant** , puis sur **Terminer**. Une boîte de dialogue s’affiche pour vous informer que l’importation a réussi et afficher votre certificat dans le dossier Certificats de la boutique.

   >[!NOTE]
   >
   >Prêtez une attention particulière aux champs **Délivrance à** et **Délivrance par** . Vous en aurez besoin à l&#39;étape suivante.

**Étape 2 : Modifiez le fichier Insight.cfg.**

Le [!DNL Insight.cfg] fichier doit être modifié pour que les outils de données puissent utiliser la fonction du magasin de certificats Windows. Certains paramètres supplémentaires doivent être spécifiés pour chaque entrée de serveur dans ce fichier. Si les paramètres sont omis, le poste de travail utilise par défaut la configuration de certificat existante. Si les paramètres sont spécifiés mais que les valeurs sont incorrectes, le poste de travail saisit un état d&#39;erreur et vous devrez vous reporter au fichier journal pour obtenir des informations sur l&#39;erreur.

1. Ouvrez le fichier **Insight.cfg** (situé dans le répertoire d’installation d’ **Insight** ).

1. Faites défiler l’écran jusqu’à l’entrée du serveur que vous souhaitez configurer. Si vous souhaitez utiliser le magasin de certificats Windows pour chaque serveur, vous devez apporter ces modifications à chaque entrée dans le vecteur des [!DNL serverInfo] objets.
1. Ajoutez ces paramètres à leur [!DNL Insight.cfg] fichier. Vous pouvez effectuer cette opération à partir du poste de travail ou manuellement en ajoutant les paramètres suivants à l&#39; [!DNL serverInfo] objet. (Veillez à utiliser des espaces au lieu de caractères de tabulation, et ne renseignez pas d&#39;autres erreurs typographiques ou de syntaxe dans ce fichier. )

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   La valeur booléenne active ou désactive la fonction. Le nom du certificat correspond à **Issuer To** dans le gestionnaire de certificats. Le nom de l’émetteur du certificat correspond à **Émis par** et le nom **de la** boutique doit correspondre au nom du magasin de certificats.

   >[!NOTE]
   >
   >Le nom &quot;Personnel&quot; dans le Gestionnaire de certificats (certmgr.msc) fait en fait référence au magasin de certificats nommé **Mon.** Par conséquent, si vous importez votre clé et votre certificat de communication SSL (.PFX) dans le magasin de certificats **personnels** comme recommandé, vous devez définir la chaîne Nom **du magasin de certificats** SSL CryptoAPI sur &quot;Mon&quot;. La définition de ce paramètre sur &quot;Personnel&quot; ne fonctionnera pas. Il s’agit d’une particularité du magasin de certificats Windows.

   Une liste complète des magasins système prédéfinis peut être obtenue ici : [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Il se peut que votre système dispose de magasins de certificats supplémentaires. Si vous souhaitez utiliser un magasin autre que &quot;Personnel&quot; (comme **Mon**), vous devez obtenir le nom canonique du magasin de certificats et le fournir dans le [!DNL Insight.cfg] fichier. (Le nom de stockage système &quot;Mon&quot; est incohérent, appelé &quot;Mon&quot; et &quot;MY&quot; par la documentation Windows. Le paramètre ne semble pas être sensible à la casse.)

1. Après avoir ajouté ces paramètres et vérifié que les valeurs correspondent à la liste dans le Gestionnaire de certificats Windows, enregistrez le [!DNL Insight.cfg] fichier.

Vous pouvez maintenant démarrer la station de travail (ou vous déconnecter/reconnecter au serveur). Les outils de données doivent charger votre certificat et votre clé depuis le magasin de certificats et se connecter normalement.

## Sortie journal {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Lorsqu’un certificat est introuvable ou non valide, ce message d’erreur est envoyé au [!DNL HTTP.log] fichier.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>La structure de journalisation L4 peut être activée en configurant le [!DNL L4.cfg] fichier (voir votre gestionnaire de compte pour la configurer).

## Utilisation de certificats personnalisés dans les outils de données {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Instructions relatives à l’utilisation des certificats personnalisés.

<!--
using-custom-certificates-DWB.xml
-->

Un certificat utilisé par le client ou le serveur Outils de données doit être signé par une autorité de certification approuvée. Les clients des outils de données reçoivent des certificats signés par l’autorité de certification Visual Sciences. Ces certificats sont approuvés par le logiciel Outils de données, car le [!DNL trust_ca_cert.pem] (fourni avec le logiciel Insight et stocké dans le répertoire **Certificats** des serveurs et des clients) contient un certificat *d’autorité de certification* racine pour l’autorité de certification Visual Sciences. Ces certificats sont utilisés à la fois pour la licence du logiciel et pour l’authentification lorsque les clients et les serveurs communiquent entre eux à l’aide de SSL. Seuls les certificats émis par l&#39;autorité de certification Visual Sciences peuvent être utilisés pour la licence, mais d&#39;autres certificats peuvent être utilisés pour la communication et l&#39;authentification. Les certificats émis par des autorités de certification autres que Visual Sciences sont appelés ci-dessous certificats *personnalisés.*

**Remarque importante :** Pour les serveurs et les clients, le logiciel Outils de données utilise les fichiers de certificat installés dans le répertoire **Certificats** du client ou du serveur ou les certificats explicitement identifiés dans sa configuration. Cependant, vous pouvez également utiliser le magasin de certificats Windows pour les clients.

Les instructions suivantes décrivent les procédures à suivre pour utiliser des certificats personnalisés pour la communication entre les clients et les serveurs des outils de données. Tous les détails ne sont pas une exigence difficile et différentes variantes du processus peuvent être utilisées. Toutefois, les procédures ci-dessous ont été testées pour fonctionner.

## Configuration des certificats client personnalisés {#section-2083fd41973e451fa404e7a4ae4da591}

1. Ajoutez le certificat de l’autorité de certification émettrice à la [!DNL trust_cert_ca.pem], qui est installé dans le répertoire **Certificats** du client et celui de chaque serveur de chaque grappe à laquelle vous souhaitez accéder à l’aide de ce certificat personnalisé.

1. Obtenez un certificat personnalisé pour chaque serveur de la grappe avec les conditions suivantes :

   1. Le certificat est formaté en tant que [!DNL .pem] certificat.
   1. Le certificat contient sa clé et n’est pas chiffré (c.-à-d. qu’il ne comporte aucun mot de passe/phrase de passe).

      Un certificat contient sa clé avec l’une des lignes suivantes :

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Pour supprimer l’expression de mot de passe d’un [!DNL .pem] certificat, procédez comme suit :

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat a le CN, O, OU, etc. comme requis pour ce client dans le [!DNL Access Control.cfg] fichier des serveurs.
   1. Le certificat a été émis avec une *finalité **** du *client* (ou des deux *serveur* **et  client).****

      Pour vérifier qu’un certificat comporte un code d’objectif du serveur et/ou du client, vous pouvez utiliser les commandes suivantes :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour un certificat de serveur, les deux commandes doivent générer les résultats suivants :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande est nécessaire pour obtenir [!DNL OK].

1. Placez le certificat dans le répertoire **Certificats** du client.
1. Dans [!DNL Insight.cfg] sous *serverInfo* pour chaque grappe que vous souhaitez utiliser ce certificat, assurez-vous que le certificat *client* personnalisé est nommé, par exemple :

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:  
     <my_custom_client_cert.pem>
   ```

## Configuration de certificats de serveur personnalisés {#setting-up-custom-server-certificates}

Cette section suppose que vous disposez d’une grappe en cours d’exécution, à l’aide de certificats émis par Visual Sciences, et que la configuration suit les pratiques courantes (par exemple, le répertoire *Composants pour les serveurs* de traitement sur le serveur maître est synchronisé avec les répertoires *Composants* de tous les processeurs de traitement).

1. Ajoutez le certificat de l’autorité de certification émettrice au certificat [!DNL trust_cert_ca.pem] qui est installé sur chaque serveur de la grappe et chaque client qui doit communiquer avec cette grappe.
1. Obtenez un certificat personnalisé pour chaque serveur de la grappe en respectant les exigences suivantes :

   1. Le certificat personnalisé est formaté en tant que [!DNL .pem] certificat.
   1. Le certificat contient sa clé et n’est pas chiffré (c.-à-d. qu’il ne comporte aucun mot de passe/phrase de passe).

      Un certificat contient sa clé s’il comporte une ligne telle que :

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Pour supprimer l’expression de mot de passe d’un [!DNL .pem] certificat, procédez comme suit :

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Le certificat possède le même CN que celui [!DNL server_cert.pem] actuellement installé sur le serveur.
   1. Le certificat a été émis dans le but de *serveur* et de *client*.

      Pour vérifier qu’un certificat comporte un code d’objectif du serveur et/ou du client, vous pouvez utiliser les commandes suivantes :

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Pour un certificat de serveur, les deux commandes doivent générer les résultats suivants :

      ```
      custom_communications_cert.pem: OK
      ```

      Pour un certificat client, seule la deuxième commande est nécessaire pour obtenir [!DNL OK].

1. Installez le certificat personnalisé de chaque serveur dans le répertoire **Certificats** du serveur en tant que [!DNL custom_communications_cert.pem].

1. A l’aide d’un éditeur de texte, ajoutez la ligne suivante au fichier **Communications.cfg** dans les répertoires *Composants* et *Composants pour les serveurs* de traitement, directement sous la première ligne ( [!DNL component = CommServer]) :

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Redémarrez tous les serveurs.

**A propos de l’avertissement d’échec de certificat**

Lorsque le serveur ou le client Insight recherche un certificat de **licence** dans le répertoire **Certificates** , il tente de valider tous les certificats (sauf [!DNL trust_ca_cert.pem]) par rapport à une copie codée en dur du certificat de l’autorité de certification Insight, qui échoue sur tout certificat personnalisé présent dans le répertoire. Le serveur émet cet avertissement :

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Cet avertissement peut être ignoré en toute sécurité.

## Chiffrement de chaîne {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Chiffrez les mots de passe et autres chaînes lors de la communication entre le client et le serveur.

<!--
string_encryption.xml
-->

Lorsque vous communiquez entre le client Outils de données (station de travail) et le serveur, vous pouvez enregistrer un paramètre Value (tel qu’un mot de passe) avec le type de *chaîne* chiffrée. Cette opération masque le paramètre et enregistre la chaîne dans le magasin *d’informations d’identification* Windows sur le serveur avec la clé correspondante renvoyée. Cette opération stocke principalement les informations d’identification utilisées dans les exportations, mais peut être utilisée pour chiffrer n’importe quel paramètre.

* Un nouveau dossier a été ajouté sur Server\**EncryptStrings**.

   C’est là que vous définissez le fichier de configuration pour chiffrer les chaînes.

* Un nouveau fichier de configuration a été ajouté à l’adresse Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent: 
     Path = Path: EncryptStrings\\*.cfg
   ```

   Ce fichier recherche les fichiers de configuration de chiffrement dans le dossier *Server*\*EncryptStrings*.

**Pour chiffrer une chaîne**:

1. Créez un fichier de configuration **EncryptedStrings.cfg** pour une chaîne dont les champs sont définis comme suit :

   ```
   Names = vector: 1 items 
    0 = NameEncryptValuePair: 
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server 
     Name = string: // Name for identifier  
     Value = string: // Value to be encrypted
   ```

   * *Valeur* : ce champ contient la chaîne de texte brut qui doit être chiffrée.

      Il s’agit uniquement du chiffrement côté serveur. Le paramètre *Value* est chiffré uniquement sur l’ordinateur serveur.

   * *Nom* : ce champ contient une valeur identifiant la chaîne chiffrée.
   * *EncryptValue* : ce champ restera vide dans le fichier de configuration d’entrée. La valeur chiffrée sera renvoyée dans ce champ.
   Vous pouvez ajouter plusieurs valeurs **NameEncryptValuePair** pour différents champs de chiffrement.

   >[!NOTE]
   >
   >Tous les champs Valeur vides seront supprimés.

1. Enregistrez le fichier **EncryptedStrings.cfg** dans le dossier Server\**EncryptStrings**.

**Fichier de sortie**

Un fichier de sortie sera généré avec le même nom que le fichier d’entrée avec un &lt;*nom*_fichier>.*extension chiffrée* . Par exemple, si le fichier d’entrée est nommé *sample.cfg* , le fichier de sortie sera appelé *sample.cfg.encrypted*.
