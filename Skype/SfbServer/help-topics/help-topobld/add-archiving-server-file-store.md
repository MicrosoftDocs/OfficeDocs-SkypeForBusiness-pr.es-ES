---
title: Agregar almacén de archivos de servidor de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: efa74bab804fee75501cdeb96c00b2055f0461e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-server-file-store"></a>Agregar almacén de archivos de servidor de archivado
 
Para habilitar el archivado del contenido de mensajería instantánea y conferencia web, debe especificar un recurso compartido de archivos que se use como almacén de archivos para las copias de todo el contenido de conferencia web. Para ello, use un recurso compartido de archivos existente o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
  
> [!IMPORTANT]
> El recurso compartido de archivos puede definirse en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología > Cuando se agrega un servidor de archivado a la topología, el generador de topología debe ser capaz de configurar el almacén de archivos de archivado y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivo que se utilizará para el almacén de archivos. Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos. 
  
Para obtener más información acerca del soporte de almacenamiento de recursos compartidos de archivos, consulte [Archivo admite el almacenamiento de información](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación de soporte y la [ubicación del archivo de registro y de datos de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación. Para obtener más información acerca de la colocación del recurso compartido de archivos, consulte [Colocación de servidores compatibles](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación de soporte.
  

