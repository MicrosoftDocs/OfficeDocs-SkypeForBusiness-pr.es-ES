---
title: Lync Server 2013 Server combinación en una implementación de grupo de servidores front-end Enterprise Edition
description: Lync Server 2013 Server combinación en una implementación de grupo de servidores front-end Enterprise Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a937cd2d58e41d56fec3c7898ebcf6725086d51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576556"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Servidor combinación en una implementación de grupo de servidores front-end Enterprise Edition para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-11_

En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede combinar en una implementación de grupo de servidores front-end 2013 de Lync Server.

<div>

## <a name="server-roles"></a>Roles de servidor

En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado se combinan en el servidor front-end, pero se requiere una configuración adicional para habilitarlos. Si no desea recopilar el servidor de mediación con el servidor front-end, puede implementarlo como un servidor de mediación independiente en un equipo individual.

Puede recopilar un servidor de aplicaciones de confianza con el servidor front-end.

Cada uno de los siguientes roles debe implementarse en un equipo separado:

  - Director

  - Servidor perimetral

  - Servidor de mediación (si no se combina con el servidor front-end)

  - Servidor Office Web Apps

No puede combinar rol de servidor de chat persistente con el servidor front-end.

</div>

<div>

## <a name="databases"></a>Databases

Puede combinar cada una de las siguientes bases de datos en el mismo servidor de base de datos:

  - Base de datos back-end

  - Base de datos de supervisión

  - Base de datos de archivado

  - Base de datos de chat persistente

  - Base de datos de cumplimiento de chat persistente

Puede combinar cualquiera de estas bases de datos, o todas ellas, en una sola instancia de SQL Server o usar una instancia independiente de SQL Server para cada una, con las siguientes limitaciones:

  - Cada instancia de SQL Server puede contener una sola base de datos back-end, una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos de chat persistente y una única base de datos de cumplimiento de chat persistente.

  - El servidor de base de datos no admite más de un grupo de servidores front-end, una implementación de archivado y una implementación de supervisión, pero puede admitir una de cada, independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.

Se puede combinar un recurso compartido de archivos con las bases de datos, como se describe más adelante en este sección.

<div>


> [!NOTE]  
> En Lync Server 2013, tiene la opción de integrar el almacenamiento de archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de la implementación. No se pueden implementar servidores que ejecuten Lync Server o componentes en los mismos servidores que el almacenamiento de Exchange.



</div>

<div>


> [!IMPORTANT]  
> Aunque se admite la combinación de las bases de datos, el tamaño de estas puede crecer rápidamente. Por ejemplo, si considera la combinación de la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede aumentar considerablemente. Por este motivo, no se recomienda combinar varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente o la base de datos de cumplimiento de chat persistente con la base de datos back-end.



</div>

</div>

<div>

## <a name="file-share"></a>Recurso compartido de archivos

El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:

  - Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition

  - Base de datos de archivado

  - Base de datos de supervisión

  - Base de datos de chat persistente

  - Base de datos de cumplimiento de chat persistente

Un solo recurso compartido de archivos se puede usar para varios grupos de servidores front-end y servidores de Standard Edition (todos ellos en el mismo sitio).

<div>


> [!NOTE]  
> En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor front-end.



</div>

</div>

<div>

## <a name="other-components"></a>Otros componentes

No puede combinar un servidor de proxy inverso, que no es un componente 2013 de Lync Server, pero es necesario en su implementación si desea admitir el uso compartido de contenido web para los usuarios federados con cualquier rol de servidor de Lync Server 2013. Sin embargo, puede implementar la compatibilidad con proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente en su organización que se usa para otras aplicaciones.

No puede combinar ningún componente de mensajería unificada (MU) de Exchange ni un componente de SharePoint con ningún rol de servidor de SharePoint.

</div>

</div>

<span> </span>

</div>

</div>

</div>

