---
description: Chiffrez les mots de passe et autres chaînes lors de la communication entre le client et le serveur.
title: Chiffrement de chaîne
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Chiffrement de chaîne{#string-encryption}

{{eol}}

Chiffrez les mots de passe et autres chaînes lors de la communication entre le client et le serveur.

Lorsque vous communiquez entre le client Data Workbench (poste de travail) et le serveur, vous pouvez enregistrer un paramètre Value (un mot de passe, par exemple) avec le Type de *EncryptedString*. Le paramètre est masqué et la chaîne est enregistrée dans la variable *Boutique d’informations d’identification Windows* sur le serveur avec la clé correspondante renvoyée. Il stocke principalement les informations d’identification utilisées dans les exportations, mais peut être utilisé pour chiffrer n’importe quel paramètre.

* Un nouveau dossier a été ajouté sur le serveur\**EncryptStrings**.

   C’est là que vous définissez le fichier de configuration pour chiffrer les chaînes.

* Un nouveau fichier de configuration a été ajouté sur Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Ce fichier interroge la variable *Serveur* dossier \*EncryptStrings* pour les fichiers de configuration de chiffrement.

**Pour chiffrer une chaîne**:

1. Créez un **EncryptedStrings.cfg** fichier de configuration pour une chaîne avec les champs suivants définis :

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Valeur* - Ce champ contient la chaîne de texte brut qui doit être chiffrée.

      Il s’agit uniquement d’un chiffrement côté serveur. Le *Valeur* est chiffré uniquement sur l’ordinateur serveur.

   * *Nom* - Ce champ contient une valeur identifiant la chaîne chiffrée.
   * *EncryptValue* - Ce champ reste vide dans le fichier de configuration d’entrée. La valeur cryptée sera renvoyée dans ce champ.

   Vous pouvez ajouter plusieurs **NameEncryptValuePair** pour différents champs de chiffrement.

   >[!NOTE]
   >
   >Tous les champs Valeur vides seront supprimés.

1. Enregistrez le **EncryptedStrings.cfg** vers le serveur\**EncryptStrings* dossier *.

**Fichier de sortie**

Un fichier de sortie sera généré avec le même nom que le fichier d’entrée avec un &lt;*filename*>.*encrypted* extension . Par exemple, si le fichier d’entrée est nommé *sample.cfg* alors le fichier de sortie sera nommé *sample.cfg.encrypted*.
