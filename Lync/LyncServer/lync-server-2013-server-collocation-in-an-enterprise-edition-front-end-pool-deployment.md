---
title: 'Lync Server 2013: Colocación de un servidor en una implementación de grupo de servidores front-end Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Colocación de un servidor en una implementación de grupo de servidores front-end Enterprise Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-11_

En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede Collocate en una implementación de grupo front-end de Lync Server 2013.

<div>

## <a name="server-roles"></a>Roles de servidor

En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado se colocan en el servidor front-end, pero se necesita una configuración adicional para habilitarlos. Si no desea Collocate el servidor de mediación con el servidor front-end, puede implementarlo como un servidor de mediación independiente en un equipo independiente.

Puede Collocate un servidor de aplicaciones de confianza con el servidor front-end.

Los siguientes roles de servidor deben implementarse en un equipo independiente:

  - Director

  - Servidor perimetral

  - Servidor de mediación (si no se ha puesto en el servidor front-end)

  - Servidor Office Web Apps

No puede Collocate rol de servidor de chat persistente con el servidor front-end.

</div>

<div>

## <a name="databases"></a>Bases de datos

Puede Collocate cada una de las siguientes bases de datos en el mismo servidor de base de datos:

  - Base de datos back-end

  - Base de datos de supervisión

  - Base de datos de archivado

  - Base de datos de chat persistente

  - Base de datos de cumplimiento de chat persistente

Puede Collocate cualquiera de estas bases de datos o cualquiera de ellas en una sola instancia de SQL Server o usar una instancia independiente de SQL Server para cada una, con las siguientes limitaciones:

  - Cada instancia de SQL Server puede contener una única base de datos back-end, una única base de datos de supervisión, una única base de datos de archivado, una única base de datos de chat persistente y una única base de datos de cumplimiento de chat persistente.

  - El servidor de base de datos no admite más de un grupo de servidores front-end, una implementación de archivado y una implementación de supervisión, pero puede admitir una de cada uno, independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.

Puede Collocate un recurso compartido de archivos con las bases de datos, tal y como se describe más adelante en esta sección.

<div>


> [!NOTE]  
> En Lync Server 2013, tiene la opción de integrar el almacenamiento de archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de su implementación. No se pueden implementar servidores que ejecuten servidores o componentes de Lync en los mismos servidores que el almacenamiento de Exchange.



</div>

<div>


> [!IMPORTANT]  
> Aunque se admite la collocation de bases de datos, el tamaño de las bases de datos puede crecer rápidamente. Por ejemplo, cuando considere collocating la base de datos de archivado con otras bases de datos, tenga en cuenta que si está archivando los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer muy grande. Por este motivo, no recomendamos que collocating varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente o la base de datos de cumplimiento de chat persistente con la base de datos back-end.



</div>

</div>

<div>

## <a name="file-share"></a>Recurso compartido de archivos

El recurso compartido de archivos puede ser un servidor independiente o se puede incluir en el mismo servidor que cualquiera de los siguientes:

  - Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front end Enterprise Edition

  - Base de datos de archivado

  - Base de datos de supervisión

  - Base de datos de chat persistente

  - Base de datos de cumplimiento de chat persistente

Un solo recurso compartido de archivos se puede usar para varios grupos front-end, servidores Standard Edition (todos en el mismo sitio).

<div>


> [!NOTE]  
> En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor front-end.



</div>

</div>

<div>

## <a name="other-components"></a>Otros componentes

No se puede Collocate un servidor proxy inverso, que no es un componente de 2013 de Lync Server, pero es necesario en la implementación si desea permitir el uso compartido de contenido web para usuarios federados con cualquier rol de servidor de Lync Server 2013. Sin embargo, puede implementar el soporte de proxy inverso para una implementación de Lync Server 2013 al configurar la compatibilidad en un servidor proxy inverso existente de su organización que se usa para otras aplicaciones.

No puede Collocate ningún componente de mensajería unificada (UM) de Exchange o componente de SharePoint con ningún rol de servidor de SharePoint.

</div>

</div>

<span> </span>

</div>

</div>

</div>

