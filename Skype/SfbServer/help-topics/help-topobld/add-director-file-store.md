---
title: Agregar almacén de archivos de director
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Debe especificar un recurso compartido de archivos para usarlo como almacén de archivos de los directores. Puede usar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos.
ms.openlocfilehash: b8873ed9a7fd4f66f60c4f1e8836c2d7a06b5f2e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-file-store"></a>Agregar almacén de archivos de director
 
Debe especificar un recurso compartido de archivos para usarlo como almacén de archivos de los directores. Puede usar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos.
  
> [!IMPORTANT]
> Al agregar directores a una topología, la publicación de topología requiere un acceso adecuado para configurar el almacén de archivos y las listas de control de acceso discrecional (DACL) en el recurso compartido de archivos que se usará para el almacén de archivos. Para ello, es necesario que al ejecutar el Generador de topologías y publicar la nueva topología, haya iniciado una sesión con una cuenta con todos los permisos de control (lectura/escritura/modificación) para el recurso compartido de archivos. 
  
Para obtener más información acerca del soporte de almacenamiento de recursos compartidos de archivos, consulte [Archivo admite el almacenamiento de información](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación de soporte y la [ubicación del archivo de registro y de datos de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación. Para obtener más información acerca de la colocación del recurso compartido de archivos, consulte [Colocación de servidores compatibles](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación de soporte. Para obtener más información acerca de cómo diseñar la topología de directores, vea [definir un único Director en el generador de topología](http://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) en la documentación de implementación.
  

