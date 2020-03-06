---
description: Le magasin de certificats Windows ne permet pas de stocker le certificat du client et sa clé privée dans le magasin de certificats Windows pour la communication SSL avec les serveurs.
title: Magasin de certificats Windows
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Magasin de certificats Windows{#windows-certificate-store}

Le magasin de certificats Windows ne permet pas de stocker le certificat du client et sa clé privée dans le magasin de certificats Windows pour la communication SSL avec les serveurs.

Le magasin de certificats Windows pour le client est une nouvelle fonctionnalité qui vous permet de stocker le certificat de communication SSL et la clé privée dans le magasin de certificats Windows plutôt que dans un `Insight/Certificates/<CertName>.pem` fichier. Il peut être préférable d’utiliser le magasin de certificats Windows si vous utilisez le magasin de certificats pour d’autres applications et souhaitez gérer les certificats au même endroit, ou pour les utilisateurs qui bénéficient de la journalisation d’audit Windows supplémentaire fournie par le magasin de certificats Windows.

>[!NOTE]
>
>Les licences avec le serveur de licences sont toujours conservées à l’aide du `<Common Name>.pem` fichier existant et le certificat obtenu à partir du magasin de certificats ne sera utilisé que pour la communication aux serveurs que vous spécifiez.

## Conditions préalables {#section-69b18600052145ff8e5299b7123e69c5}

1. Vous devez avoir accès au [!DNL certmgr.msc] fichier avec la possibilité d’importer un certificat et une clé dans le magasin **personnel** . (Cela doit être vrai par défaut pour la plupart des utilisateurs de Windows.)

1. L’utilisateur effectuant la configuration doit disposer d’une copie de l’outil de ligne de commande **OpenSSL** .
1. Le serveur et le client doivent déjà être configurés pour utiliser un certificat SSL personnalisé, comme décrit à la section [Utilisation de certificats](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)personnalisés, qui donne des instructions pour stocker le certificat client dans le magasin de certificats Windows au lieu de le stocker dans le répertoire **Certificats** .

## Configuration du magasin de certificats Windows {#section-3629802122e947d4b4f63e8b732cfe27}

Le magasin de certificats Windows pour les clients est activé en procédant comme suit :

**Étape 1 : Importez le certificat SSL et la clé privée de l’utilisateur dans le magasin de certificats Windows.**

Dans [Utilisation des certificats](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) personnalisés, vous êtes invité à placer le certificat et la clé SSL dans le répertoire suivant :

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Le nom du certificat est `<Common Name>.pem` (par exemple [!DNL Analytics Server 1.pem](et non le [!DNL trust_ca_cert.pem] fichier).

Avant de pouvoir importer le certificat et la clé privée, ils doivent être convertis à partir de . [!DNL pem] dans un [!DNL .pfx] format, par exemple [!DNL pkcs12.pfx] ).

1. Ouvrez une invite de commande ou un terminal et accédez au répertoire :

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
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
