---
title: 'Lync Server 2013: componentes y topologías para archivado'
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
ms.openlocfilehash: ec153b237df086f3622acc70c104bddc64fef28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502617"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Componentes y topologías para el archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Si desea archivar el contenido de mi y Conferencia de Lync Server 2013, puede implementar el archivado en Lync Server.

<div>

## <a name="archiving-components"></a>Componentes de archivado

La característica Archivado incluye los siguientes componentes:

  - **Agentes de archivado**   Los agentes de archivado (también llamados agentes de colección de datos unificada) se instalan y activan automáticamente en cada grupo de servidores front-end y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que se habilite y configure correctamente el archivado.

  - **Almacenamiento de datos de archivado**. El almacenamiento de datos para Lync Server 2013 puede ser cualquiera de los siguientes:
    
      - Almacenamiento de Exchange 2013. Si habilita la opción de integración de Microsoft Exchange, los buzones de correo de usuario hospedados en el servidor Exchange 2013 usan el almacenamiento de Exchange 2013 para los datos archivados, pero solo si los buzones se han puesto en retención de In-Place.
    
      - Almacenamiento de SQL Server. Si tiene usuarios en su implementación hospedados en Lync Server 2013, puede configurar las bases de datos de archivado que ejecutan una versión compatible de SQL Server para habilitar el archivado para esos usuarios.

El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o que el servidor Standard Edition.

Para obtener una lista de requisitos de hardware y software para el archivado, consulte Supported [hardware for Lync server 2013](lync-server-2013-supported-hardware.md) y [Server Software and Infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación sobre compatibilidad.

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

Implemente el archivado en cada grupo que tenga usuarios que requieran compatibilidad de archivado. El archivado se ejecuta en los servidores front-end de los grupos de servidores Enterprise Edition y en los servidores Standard Edition. El almacenamiento de datos de archivado puede ser el siguiente:

  - Integrada con el almacenamiento de Exchange 2013

  - Implementación mediante bases de datos de SQL Server independientes

Si su implementación de Exchange 2013 no incluye a todos los usuarios de su implementación de Lync Server, debe usar la integración de Microsoft Exchange para los usuarios cuyos buzones se encuentran en servidores de Exchange 2013 y debe implementar bases de datos de SQL Server independientes para el resto de los usuarios de Lync que se vayan a usar para el archivado.

</div>

<div>

## <a name="supported-collocation"></a>Escenarios de instalación compatibles

Lync Server 2013 admite una amplia variedad de escenarios de combinación, lo que le permite ahorrarse los costos de hardware mediante la ejecución de varios componentes en un servidor (si tiene una organización pequeña) o para ejecutar componentes individuales en diferentes servidores (si tiene una organización más grande que necesita escalabilidad y rendimiento). Los factores de escalabilidad se deben tener en cuenta antes de decidir si los componentes se van a combinar.

El archivado se implementa en los servidores front-end de un grupo de servidores o servidores Standard Edition. Para obtener más información sobre los componentes que se pueden combinar allí, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.

Si usa bases de datos de SQL Server independientes para el archivado, en lugar de integrar el almacenamiento con el almacenamiento de Exchange 2013, puede combinar la base de datos de archivado con cualquiera de los siguientes elementos:

  - Base de datos de supervisión

  - Base de datos back-end de un grupo de servidores front-end de Enterprise Edition

<div>


> [!NOTE]  
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Sin embargo, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no se recomienda la combinación de la base de datos de archivado con la base de datos back-end.



</div>

Si combina la base de datos de archivado con la base de datos de supervisión, la base de datos back-end, o con ambas, puede usar una sola instancia de SQL para cualquiera de las bases de datos o pude usar una instancia SQL independiente para cada base de datos, con la siguiente limitación:

  - Cada instancia de SQL puede contener únicamente una sola base de datos back-end, una sola base de datos de supervisión y una sola base de datos de archivado.

Para obtener más información sobre la combinación de todos los roles de servidor y las bases de datos, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.

</div>

</div>

<span> </span>

</div>

</div>

</div>

