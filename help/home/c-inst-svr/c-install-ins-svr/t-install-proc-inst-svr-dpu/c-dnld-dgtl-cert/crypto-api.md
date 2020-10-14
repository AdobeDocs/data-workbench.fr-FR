---
description: La boutique de certificats Windows vous permet de stocker le certificat et la clé privée du client pour la communication SSL avec les serveurs.
title: Boutique de certificats Windows
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: ht
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Boutique de certificats Windows {#windows-certificate-store}

La boutique de certificats Windows vous permet de stocker le certificat et la clé privée du client pour la communication SSL avec les serveurs.

La boutique de certificats Windows destinée au client constitue une nouvelle fonctionnalité qui vous permet de stocker le certificat de communication SSL ainsi que la clé privée dans la boutique de certificats Windows plutôt que dans un fichier `Insight/Certificates/<CertName>.pem`. Il peut être préférable d’utiliser la boutique de certificats Windows si vous utilisez la boutique de certificats pour d’autres applications et souhaitez gérer tous les certificats à un seul endroit. La boutique de certificats peut aussi être utile aux utilisateurs qui apprécient la journalisation d’audit Windows complémentaire qu’elle fournit.

>[!NOTE]
>
>L’obtention de licences avec le serveur de licences est toujours possible à l’aide du fichier `<Common Name>.pem` existant, et le certificat obtenu à partir de la boutique de certificats sera uniquement utilisé à des fins de communication avec les serveurs que vous précisez.

## Conditions préalables {#section-69b18600052145ff8e5299b7123e69c5}

1. Vous devez avoir accès au fichier [!DNL certmgr.msc] avec possibilité d’importer un certificat et une clé dans la boutique **personnelle**. (La plupart des utilisateurs Windows devraient remplir par défaut ces conditions.)

1. L’utilisateur qui effectue la configuration doit disposer d’une copie de l’outil de ligne de commande **OpenSSL**.
1. Le serveur et le client doivent déjà être configurés pour utiliser un certificat SSL personnalisé, comme décrit dans la section [Utilisation de certificats personnalisés](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd). Celle-ci explique comment stocker le certificat du client dans la boutique de certificats Windows au lieu de le stocker dans le répertoire **Certificats**.

## Configuration de la boutique de certificats Windows {#section-3629802122e947d4b4f63e8b732cfe27}

La boutique de certificats Windows pour les clients est activée de la manière suivante :

**Étape 1 : importez le certificat SSL et la clé privée de l’utilisateur dans la boutique de certificats Windows.**

Dans [Utilisation de certificats personnalisés](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd), vous êtes invité à placer le certificat et la clé SSL dans le répertoire suivant :

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Le nom du certificat est `<Common Name>.pem` (par exemple [!DNL Analytics Server 1.pem], et non pas le fichier [!DNL trust_ca_cert.pem].

Avant que le certificat et la clé privée puissent être importés, ils doivent être convertis depuis un format .[!DNL pem] vers un format [!DNL .pfx], par exemple [!DNL pkcs12.pfx]).

1. Ouvrez une invite de commandes ou un terminal et accédez au répertoire :

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
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
