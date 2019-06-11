---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de258bff926e2e100fa7c9a4952a4d70ca64373
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Después de implementar el grupo piloto, debe comprobar la coexistencia de las dos agrupaciones mediante las herramientas administrativas para ver la información del grupo. Para los grupos de 2013 y los grupos heredados de Lync Server, debe usar las herramientas del panel de control y del generador de topologías de Lync Server 2013.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Comprobar que los servicios de Lync Server 2013 se han iniciado

1.  En el servidor front-end de Lync Server 2013, vaya al subprograma Servicios de herramientas\\administrativas.

2.  Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:

**Servicios de Lync Server 2013**

![Lista de servicios de Lync Server iniciada] (images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Lista de servicios de Lync Server iniciada")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Abrir el panel de control de Lync Server 2013

Desde el servidor front-end de su implementación de Lync Server 2013, abra el panel de control de Lync Server 2013 y seleccione el grupo de servidores de Lync Server 2010. Repita el procedimiento para abrir el grupo de servidores de Lync Server 2013.

**Abrir el panel de control de Lync Server 2013**

![Cuadro de diálogo Seleccionar dirección URL] (images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Cuadro de diálogo Seleccionar dirección URL")

<div>


> [!IMPORTANT]  
> En Lync Server 2013, debe actualizar Silverlight a la versión 5 antes de usar el panel de control de Lync Server.



</div>

Esta topología incluye ahora los roles de servidor de Lync Server 2010 y Lync Server 2013.

**Página de topología del panel de control 2013 de Lync Server**

![Panel de control de Lync Server-página de topología] (images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Panel de control de Lync Server-página de topología")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>No intente abrir la topología en el generador de topología de Lync Server 2010

Si intenta abrir la topología con el generador de topología de Lync Server 2010, encontrará el error siguiente. La topología solo se puede ver con el generador de topología de Lync Server 2013. El generador de topología de Lync Server 2013 debe usarse para crear grupos para Lync Server 2013 y Lync Server 2010.

**Mensaje de error del generador de topología 2010 de Lync Server**

![Error de acoplamiento de MMC del generador de topología de Lync Server] (images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Error de acoplamiento de MMC del generador de topología de Lync Server")

</div>

</div>

<span> </span>

</div>

</div>

</div>

