---
title: 'Lync Server 2013: componentes necesarios para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a87fa004cabe90d8a4dc79771295af8fc61a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Componentes necesarios para el Director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

El único componente necesario para crear y configurar un director es implementar el rol de servidor Director. Para ello, puede usar el generador de topologías y definir un grupo de un solo equipo o un grupo de varios equipos en el nodo de grupo de directores. Una vez que haya definido el director o el grupo de directores, ejecute el Asistente para la implementación de Lync Server en el equipo que será director. En el caso de un grupo de directores, ejecute el Asistente para la implementación de Lync Server en cada servidor que vaya a ser miembro del grupo.

<div>

## <a name="topologies"></a>Topologías

Puede implementar un servidor de Director único o un grupo de directores. El director es siempre un servidor o grupo de servidores independiente, no combinado con ningún otro rol de servidor en Lync Server 2013.

<div>


> [!NOTE]  
> Si no implementa los directores, el servidor front-end o el grupo de servidores front-end asumirán el rol de director.



</div>

Un grupo de directores debe tener carga equilibrada. Puede hacer uno de los pasos siguientes:

  - Cree una topología que use un equilibrador de carga de hardware para los servicios web y el equilibrio de carga del sistema de nombres de dominio (DNS) para los otros tipos de tráfico.
    
    [Grupo de Director escalado-equilibrio de carga de DNS y equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Cree una topología que use un equilibrador de carga de hardware para el equilibrio de carga necesario para el grupo de directores.
    
    [Grupo de Director escalado-equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

