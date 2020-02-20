---
title: Lync Server 2013 Server combinación en una implementación de servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7390c3cee8be94f6bead96ff990e380b06011eb7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Combinación de servidor en una implementación de servidor Standard Edition para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-20_

En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede combinar en una implementación de servidor de Lync Server 2013 Standard Edition.

<div>

## <a name="server-roles"></a>Roles de servidor

En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado están combinados en el servidor Standard Edition, pero se requiere una configuración adicional para habilitarlos. Puede implementar el servicio de mediación en servidores distintos.

Puede recopilar un servidor de aplicaciones de confianza con el servidor Standard Edition.

Cada uno de los siguientes roles de servidor deben implementarse en un equipo aparte:

  - Dirección

  - Servidor perimetral

  - Servidor de mediación (si no se combina con el servidor de Standard Edition)

  - Servidor Office Web Apps

</div>

<div>

## <a name="databases"></a>Databases

De manera predeterminada, la base de datos back-end de SQL Server Express se combina con el servidor Standard Edition. No se puede mover a otro equipo diferente. Con una excepción, no puede combinar otras bases de datos en el servidor Standard Edition. Si opta por implementar el servidor de chat persistente en un servidor Standard Edition, puede combinar la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente en el mismo servidor Standard Edition.

Se puede combinar cada una de las siguientes bases de datos en un único servidor de base de datos:

  - Base de datos de supervisión

  - Base de datos de archivado

  - Una base de datos back-end para un grupo de servidores front-end de Enterprise Edition

Se puede combinar cualquiera de estas bases de datos, o todas ellas, en una única instancia de SQL o usar una instancia de SQL diferente para cada una, con las siguientes restricciones:

  - Cada instancia de SQL puede contener únicamente una base de datos back-end (para un grupo de servidores front-end de Enterprise Edition), una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos de chat persistente o una sola base de datos de cumplimiento de chat persistente.

  - El servidor de base de datos no admite más de un grupo de servidores front-end Enterprise Edition, un servidor que ejecuta el archivado, un servidor que ejecuta la supervisión, una base de datos de chat persistente y una base de datos de cumplimiento de chat persistente, pero puede admitir uno de cada uno de ellos. independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.

Se puede combinar un recurso compartido de archivos con las bases de datos, como se describe más adelante en este sección.

<div>


> [!NOTE]  
> En Lync Server 2013, tiene la opción de integrar el almacenamiento de la supervisión y el archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de la implementación. No se pueden implementar servidores que ejecuten Lync Server o componentes en los mismos servidores que el almacenamiento de Exchange.



</div>

<div>


> [!IMPORTANT]  
> Aunque se admite la combinación de las bases de datos, el tamaño de estas puede crecer rápidamente. Por ejemplo, si considera la combinación de la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede aumentar considerablemente. Por este motivo, no se recomienda combinar varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente con la base de datos back-end de un grupo de servidores Enterprise.



</div>

</div>

<div>

## <a name="file-shares"></a>Recursos compartidos de archivos

El recurso compartido de archivo puede ser un servidor aparte o se puede combinar en el mismo servidor que cualquiera de los siguientes, o todos ellos:

  - Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition

  - Base de datos de archivado

  - Base de datos de supervisión

  - Base de datos de chat persistente

  - Base de datos de cumplimiento de chat persistente

Un solo recurso compartido de archivos se puede usar para varios grupos de servidores front-end y servidores de Standard Edition (todos ellos en el mismo sitio).

<div>


> [!NOTE]  
> En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor Standard Edition.



</div>

</div>

<div>

## <a name="other-components"></a>Otros componentes

No puede combinar un servidor de proxy inverso, que no es un componente 2013 de Lync Server, pero es necesario en su implementación si desea admitir el uso compartido de contenido web para los usuarios federados con cualquier rol de servidor de Lync Server 2013. Sin embargo, puede implementar la compatibilidad con proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente en su organización que se usa para otras aplicaciones.

No puede combinar ningún componente de mensajería unificada de Exchange o componente de SharePoint con ningún rol de Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

