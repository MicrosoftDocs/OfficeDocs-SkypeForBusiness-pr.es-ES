---
title: Copia de seguridad de almacenes de archivos
TOCTitle: Copia de seguridad de almacenes de archivos
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202167(v=OCS.15)
ms:contentKeyID: 52061603
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Copia de seguridad de almacenes de archivos

 

_**Última modificación del tema:** 2013-02-17_

La copia de seguridad de los almacenes de archivos de Lync Server incluye todos los archivos y carpetas utilizados por los componentes de Lync Server.

## Para crear copias de seguridad de almacenes de archivos

1.  Para buscar las ubicaciones específicas de los almacenes de archivos de Lync Server, abra la Generador de topologías y busque en el nodo **Almacenes de archivos**.

2.  Utilice Robocopy u otra herramienta de administración de sistemas de archivos para copiar cada Almacén de archivos a $Backup\\filestore.

