---
description: Exemple de code de feuille de style Mail XSL.
title: Exemple de feuille de style Mail XSL
uuid: 846ddf22-e6da-4d37-ba50-d75f850b9a3f
exl-id: 4b868da4-1a3b-454c-940c-8ffd9644c92a
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '24'
ht-degree: 41%

---

# Exemple de feuille de style Mail XSL{#sample-mail-xsl-style-sheet}

Exemple de code de feuille de style Mail XSL.

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="https://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
<html>
<body>
<h2>Reports</h2>
<xsl:for-each select="REPORTS/REPORT[@format!='xls']">
<img><xsl:attribute name="src">cid:<xsl:value-of select="PATH"/></xsl:attribute></img><p/>
</xsl:for-each>
</body>
</html>
</xsl:template>
</xsl:stylesheet>
```
