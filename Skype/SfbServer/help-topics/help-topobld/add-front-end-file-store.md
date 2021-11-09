---
title: Agregar almacén de archivos front-end
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Debe especificar el recurso compartido de archivos que debe usarse como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 85e1e68c64e8175968211cccac83bcf6302cb5e0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844553"
---
# <a name="add-front-end-file-store"></a>Agregar almacén de archivos front-end

Debe especificar el recurso compartido de archivos que debe usarse como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.

> [!IMPORTANT]
> El recurso compartido de archivos no se puede encontrar en Enterprise Edition servidor front-end, pero se puede encontrar en un Standard Edition servidor.

> [!IMPORTANT]
> El recurso compartido de archivos puede definirse en Topology Builder antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología.

> [!IMPORTANT]
> Al agregar un grupo de servidores front-end de Enterprise Edition o un servidor Standard Edition en la topología, Topology Builder debe poder instalar el recurso compartido de archivos y configurar listas de control de acceso discrecional en el recurso compartido de archivos para usarse almacén de archivos. Esto implica que, al ejecutar Topology Builder para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos.

Para obtener más información acerca de la compatibilidad con almacenamiento para recursos compartidos de archivos, consulte [File Storage Supportability documentation](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) y SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) en la documentación de implementación. Para más información sobre la combinación del recurso compartido de archivos, consulte [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) en la documentación sobre compatibilidad. Para obtener más información sobre cómo diseñar la topología de un grupo de servidores front-end de Enterprise Edition, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) en la documentación sobre implementación.