---
description: Chiffrez les mots de passe et autres chaînes lors de la communication entre le client et le serveur.
title: Chiffrement de chaîne
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Chiffrement de chaîne{#string-encryption}

Chiffrez les mots de passe et autres chaînes lors de la communication entre le client et le serveur.

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
