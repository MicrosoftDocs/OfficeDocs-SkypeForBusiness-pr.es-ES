---
title: 'Lync Server 2013: Componentes y topologías para archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Componentes y topologías para archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Si desea archivar el contenido de mensajería instantánea y de conferencia de Lync Server 2013, puede implementar el archivado en Lync Server.

<div>

## <a name="archiving-components"></a>Archivar componentes

La característica de archivado incluye los siguientes componentes:

  - **Agentes de archivado**. Los agentes de archivado (también conocidos como agentes unificados de recopilación de datos) se instalan y activan automáticamente en todos los servidores front-end y Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se captura ningún mensaje hasta que se habilite el archivado y se configure correctamente.

  - **Almacenamiento de datos de archivado**. El almacenamiento de datos para Lync Server 2013 puede ser cualquiera de los siguientes:
    
      - Almacenamiento de Exchange 2013. Si habilita la opción de integración de Microsoft Exchange, los buzones de usuario alojados en el servidor de Exchange 2013 usan almacenamiento de Exchange 2013 para los datos archivados, pero solo si los buzones se han puesto en conservación local.
    
      - Almacenamiento de SQL Server. Si tiene usuarios de su implementación que estén alojados en Lync Server 2013, puede configurar bases de datos de archivado que ejecuten una versión compatible de SQL Server para habilitar el archivado de esos usuarios.

El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o el servidor Standard Edition.

Para obtener una lista de los requisitos de hardware y software para el archivado, consulte [hardware admitido para Lync server 2013](lync-server-2013-supported-hardware.md) y compatibilidad de la [infraestructura y el software de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de soporte técnico.

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

Implemente el archivado en cada grupo de servidores que tenga usuarios que necesiten compatibilidad de archivado. El archivado se ejecuta en servidores front-end de los grupos de servidores Enterprise Edition y en servidores Standard Edition. El almacenamiento de datos de archivado puede ser el siguiente:

  - Integrado con el almacenamiento de Exchange 2013

  - Implementada con bases de datos SQL Server independientes

Si su implementación de Exchange 2013 no incluye todos los usuarios de su implementación de Lync Server, debe usar la integración de Microsoft Exchange para los usuarios cuyos buzones se encuentran en los servidores de Exchange 2013 y debe implementar bases de datos de SQL Server independientes para todas las demás Usuarios de Lync que se usarán para el archivado.

</div>

<div>

## <a name="supported-collocation"></a>Collocation compatibles

Lync Server 2013 admite una gran variedad de escenarios de collocation, lo que le permite ahorrar dinero al ejecutar varios componentes en un servidor (si tiene una pequeña organización) o ejecutar componentes individuales en diferentes servidores (si tiene un mayor organización que necesita escalabilidad y rendimiento). Los factores de escalabilidad se deben considerar sin duda antes de decidir si se Collocate los componentes.

El archivado se implementa en los servidores front-end de un grupo de servidores o servidores Standard Edition. Para obtener más información sobre los componentes que se pueden colocar aquí, consulte [compatibilidad de servidor collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de soporte técnico.

Si usa bases de datos de SQL Server independientes para archivar, en lugar de o además de integrar el almacenamiento con el almacenamiento de Exchange 2013, puede Collocate la base de datos de archivado con cualquiera de los siguientes:

  - Base de datos de supervisión

  - Base de datos back-end de un grupo de servidores front-end Enterprise Edition

<div>


> [!NOTE]  
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Pero, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no recomendamos la combinación de la base de datos de archivado con la base de datos back-end.



</div>

Si Collocate la base de datos de archivado con la base de datos de supervisión, la base de datos back-end o ambas bases de datos, puede usar una única instancia de SQL para cualquiera de las bases de datos o todas ellas, o bien, puede usar una instancia SQL independiente para cada base de datos, con lo siguiente: limitación

  - Cada instancia de SQL puede contener una única base de datos back-end, una única base de datos de supervisión y una única base de datos de archivado.

Para más información sobre collocation de todos los roles de servidor y bases de datos, consulte compatibilidad con [servidores de collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de soporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

