---
title: Agregar almacén de archivos front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos del servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 7a4761beb798e52d848b7c0c42c3157f7a5da400
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235458"
---
# <a name="add-front-end-file-store"></a>Agregar almacén de archivos front-end

Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos del servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.

> [!IMPORTANT]
> El recurso compartido de archivos no puede estar en el grupo de servidores front-end Enterprise Edition, sino en un servidor Standard Edition.

> [!IMPORTANT]
> El recurso compartido de archivos se puede definir en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos se debe crear en la ubicación indicada antes de publicar la topología

> [!IMPORTANT]
> Al agregar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition en la topología, el Generador de topologías debe poder instalar el recurso compartido de archivos y configurar listas de control de acceso discrecionales en el recurso compartido de archivos para usarse para el almacén de archivos. Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.

Para obtener información detallada sobre la compatibilidad de almacenamiento para los recursos compartidos de archivos, consulte [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) en la documentación sobre compatibilidad y [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación. Para obtener información detallada sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación sobre compatibilidad. Para obtener información detallada sobre cómo diseñar la topología de un grupo de servidores front-end Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación sobre implementación.


