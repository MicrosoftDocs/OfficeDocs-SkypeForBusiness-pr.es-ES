---
title: 'Lync Server 2013: Componentes requeridos para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c80002d0c91853be1523f6ce1bedfdccef72a68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Componentes requeridos para el director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

El único componente necesario para crear y configurar un director es implementar la función de servidor de director. Para ello, use el generador de topología y defina un único grupo de equipos o un grupo de varios equipos en el nodo de grupo de directores. Una vez que haya definido el grupo de directores o directores, ejecute el Asistente para la implementación de Lync Server en el equipo que será director. En el caso de un grupo de directores, ejecute el Asistente para la implementación de Lync Server en cada servidor que vaya a ser miembro del grupo.

<div>

## <a name="topologies"></a>Topologías

Puede implementar un servidor de un solo Director o un grupo de directores. El director es siempre un servidor o grupo de servidores separado, no en función de ningún otro rol de servidor de Lync Server 2013.

<div>


> [!NOTE]  
> Si no implementa directores, el servidor front-end o el grupo de servidores front-end asumirán el rol de director.



</div>

Un grupo de directores debe tener equilibrio de carga. Puede realizar una de las siguientes acciones:

  - Cree una topología que use un equilibrador de carga de hardware para los servicios web y el equilibrio de carga del sistema de nombres de dominio (DNS) para los otros tipos de tráfico.
    
    [Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Cree una topología que use un equilibrador de carga de hardware para el equilibrio de carga necesario para el grupo de directores.
    
    [Grupo de servidores de director escalado - Equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

