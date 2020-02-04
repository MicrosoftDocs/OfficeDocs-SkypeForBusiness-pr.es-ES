---
title: 'Lync Server 2013: Colocación de un servidor en una implementación de servidores de Standard Edition'
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
ms.openlocfilehash: 6fa25655fd9bdd2551e10d1fbbf0de617b89be64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Colocación de un servidor en una implementación de servidores de Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-20_

En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede Collocate en una implementación de servidor Standard Edition de Lync Server 2013.

<div>

## <a name="server-roles"></a>Roles de servidor

En Lync Server 2013, el servicio conferencia A/V, servicio de mediación, supervisión y archivado están colocados en el servidor Standard Edition, pero se necesita una configuración adicional para habilitarlos. Puede implementar el servicio de mediación en servidores diferentes.

Puede Collocate un servidor de aplicaciones de confianza con un servidor Standard Edition.

Los siguientes roles de servidor deben implementarse en un equipo independiente:

  - Director

  - Servidor perimetral

  - Servidor de mediación (si no se ha puesto en el servidor Standard Edition)

  - Servidor Office Web Apps

</div>

<div>

## <a name="databases"></a>Bases de datos

De forma predeterminada, la base de datos back-end de SQL Server Express se encuentra en el servidor Standard Edition. No puedes moverlo a otro equipo. Con una excepción, no se pueden Collocate otras bases de datos en el servidor Standard Edition. Si elige implementar un servidor de chat persistente en un servidor Standard Edition, puede Collocate la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente en el mismo servidor Standard Edition.

Puede Collocate cada una de las siguientes bases de datos en un único servidor de base de datos:

  - Base de datos de supervisión

  - Base de datos de archivado

  - Una base de datos back-end para un grupo de servidores front end Enterprise Edition

Puede Collocate cualquiera de estas bases de datos, o cualquiera de ellas, en una única instancia de SQL o usar una instancia de SQL diferente para cada una, con las siguientes limitaciones:

  - Cada instancia de SQL puede contener una única base de datos back-end (para un grupo de servidores front end Enterprise Edition), una única base de datos de supervisión, una base de datos de archivado única, una base de datos de chat persistente y una única base de datos de cumplimiento persistente.

  - El servidor de base de datos no es compatible con más de un grupo de servidores front-end Enterprise Edition, un servidor que ejecuta el archivado, un servidor que ejecuta supervisión, una base de datos de chat persistente y una única base de datos de cumplimiento persistente, pero puede admitir una de cada uno. independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.

Puede Collocate un recurso compartido de archivos con las bases de datos, tal y como se describe más adelante en esta sección.

<div>


> [!NOTE]  
> En Lync Server 2013, tiene la opción de integrar el almacenamiento de supervisión y archivado con el almacenamiento de Exchange 2013 para algunos o todos los usuarios de su implementación. No se pueden implementar servidores que ejecuten servidores o componentes de Lync en los mismos servidores que el almacenamiento de Exchange.



</div>

<div>


> [!IMPORTANT]  
> Aunque se admite la collocation de bases de datos, el tamaño de las bases de datos puede crecer rápidamente. Por ejemplo, cuando considere collocating la base de datos de archivado con otras bases de datos, tenga en cuenta que si está archivando los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer muy grande. Por este motivo, no recomendamos que collocating varias bases de datos, especialmente la base de datos de archivado, la base de datos de chat persistente y la base de datos de cumplimiento persistente con la base de datos back-end de un grupo de empresas.



</div>

</div>

<div>

## <a name="file-shares"></a>Archivos compartidos

El recurso compartido de archivos puede ser un servidor independiente o se puede incluir en el mismo servidor que cualquiera de los siguientes:

  - Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front end Enterprise Edition

  - Base de datos de archivado

  - Base de datos de supervisión

  - Base de datos de chat persistente

  - Base de datos de cumplimiento de chat persistente

Un solo recurso compartido de archivos se puede usar para varios grupos front-end, servidores Standard Edition (todos en el mismo sitio).

<div>


> [!NOTE]  
> En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor Standard Edition.



</div>

</div>

<div>

## <a name="other-components"></a>Otros componentes

No se puede Collocate un servidor proxy inverso, que no es un componente de 2013 de Lync Server, pero es necesario en la implementación si desea permitir el uso compartido de contenido web para usuarios federados con cualquier rol de servidor de Lync Server 2013. Sin embargo, puede implementar el soporte de proxy inverso para una implementación de Lync Server 2013 al configurar la compatibilidad en un servidor proxy inverso existente de su organización que se usa para otras aplicaciones.

No puede Collocate ningún componente de mensajería unificada de Exchange o componente de SharePoint con ningún rol de 2013 de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

