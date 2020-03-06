---
description: Mise à jour de sécurité du portail de rapports des outils de données.
title: Portail de rapports DWB 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Portail de rapports DWB 2.1{#dwb-report-portal}

Mise à jour de sécurité du portail de rapports des outils de données.

**Mise à jour de sécurité importante**

Le portail de rapports propose désormais des algorithmes de hachage plus puissants avec prise en charge de l’envoi. Si vous effectuez une mise à niveau vers Report Portal 2.1, ajoutez un nouveau champ Texte, PasswordSalt, dont la taille du champ est de 20 caractères dans la base de données users.mdb. Ce champ est obligatoire pour stocker le mot de passe sel.
