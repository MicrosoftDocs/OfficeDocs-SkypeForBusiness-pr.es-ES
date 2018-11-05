---
title: Restaurar la configuración de grupos de respuesta
TOCTitle: Restaurar la configuración de grupos de respuesta
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202174(v=OCS.15)
ms:contentKeyID: 52061637
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar la configuración de grupos de respuesta

 

_**Última modificación del tema:** 2013-02-18_

Si implementó el Aplicación de grupo de respuesta y necesita restaurar un servidor back-end o un Servidor Standard Edition, también tendrá que restaurar las opciones de configuración de Grupo de respuesta.

## Para restaurar las opciones de configuración del grupo de respuesta

1.  En la línea de comandos, escriba:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

