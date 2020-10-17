---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8958fbf22e096a1d9fef03afd3aac3b4656ed0e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515937"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Después de implementar el grupo piloto, verifique la coexistencia de los dos grupos de servidores con las herramientas administrativas para ver la información del grupo. En el caso de los grupos de servidores de Lync Server 2013 y los grupos de servidores heredados, debe usar las herramientas del panel de control de Lync Server 2013 y el generador de topologías.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Compruebe que se han iniciado los servicios de Lync Server 2013

1.  Desde el servidor front-end de Lync Server 2013, vaya al \\ subprograma Servicios de herramientas administrativas.

2.  Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:

**Servicios de Lync Server 2013**

![Lista de servicios de Lync Server iniciada](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Lista de servicios de Lync Server iniciada")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Abrir el panel de control de 2013 de Lync Server

Desde el servidor front-end en su implementación de Lync Server 2013, abra el panel de control de Lync Server 2013 y seleccione el grupo de servidores de Lync Server 2010. Repita el procedimiento para abrir el grupo de servidores de Lync Server 2013.

**Abra el panel de control de Lync Server 2013.**

![Cuadro de diálogo Seleccionar dirección URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Cuadro de diálogo Seleccionar dirección URL")

<div>


> [!IMPORTANT]  
> En Lync Server 2013, debe actualizar Silverlight a Silverlight versión 5 antes de usar el panel de control de Lync Server.



</div>

Esta topología incluye ahora los roles de servidor Lync Server 2010 y Lync Server 2013.

**Página Topología del panel de control de Lync Server 2013**

![Panel de control de Lync Server-página de topología](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Panel de control de Lync Server-página de topología")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>No intente abrir la topología en el generador de topologías de Lync Server 2010

Si intenta abrir la topología con el generador de topologías de Lync Server 2010, encontrará el siguiente error. La topología solo se puede ver con el generador de topologías de Lync Server 2013. El generador de topologías de Lync Server 2013 debe usarse para crear grupos para Lync Server 2013 y Lync Server 2010.

**Mensaje de error del Generador de topologías de Lync Server 2010**

![Error de instantánea de MMC del generador de topologías de Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Error de instantánea de MMC del generador de topologías de Lync Server")

</div>

</div>

<span> </span>

</div>

</div>

</div>

