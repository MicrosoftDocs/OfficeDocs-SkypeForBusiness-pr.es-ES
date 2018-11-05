---
title: Restaurar un almacén de archivos
TOCTitle: Restaurar un almacén de archivos
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202180(v=OCS.15)
ms:contentKeyID: 52061667
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar un almacén de archivos

 

_**Última modificación del tema:** 2013-02-18_

Los almacenes de archivos en Standard Edition se suelen ubicar en el Servidor Standard Edition, mientras que en Enterprise Edition se encuentran por lo general en un clúster o un servidor de archivos. El procedimiento siguiente describe cómo restaurar un Almacén de archivos.

## Para restaurar un almacén de archivos

1.  Si se produce un error en un Almacén de archivos, copie el Almacén de archivos correspondiente de $Backup\\ en la ubicación del Almacén de archivos en el servidor de archivos o el Servidor Standard Edition y, tras ello, comparta la carpeta.
    
    > [!IMPORTANT]  
    > La ruta de acceso y el nombre de archivo del Almacén de archivos restaurado deben ser exactamente iguales a los del Almacén de archivos del que se ha hecho la copia de seguridad. De este modo, los componentes que usan los archivos podrán acceder a ellos.
    


2.  Si procede, establezca las listas de control de acceso (ACL) del Almacén de archivos. En la línea de comandos, escriba lo siguiente:
    
        Enable-CsTopology
    

    > [!NOTE]
    > Este paso solo es necesario si no ha ejecutado el Generador de topologías en el transcurso de la restauración.


