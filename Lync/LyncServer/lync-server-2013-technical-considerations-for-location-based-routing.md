---
title: 'Lync Server 2013: consideraciones técnicas para el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdebdccd0584d31b27120709212be674e8d3c2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Consideraciones técnicas sobre el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Al planear el enrutamiento basado en ubicación, debe tener en cuenta el impacto en los siguientes escenarios.

<div>

## <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del grupo principal a un grupo de copia de seguridad, así como cuando se restauran operaciones normales en el grupo principal, el enrutamiento basado en ubicación permanece aplicado en todo momento durante un procedimiento de recuperación ante desastres.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

La configuración del enrutamiento basado en ubicación afecta a la planificación de dónde se implementan las puertas de enlace asociadas a las aplicaciones de sucursal con funciones de supervivencia. La puerta de enlace asociada a SBA debe estar ubicada en el mismo sitio de red que la aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios hospedados en su aplicación de sucursal con funciones de supervivencia no tendrán permiso para realizar llamadas salientes si está configurado el enrutamiento basado en ubicación. Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central no esté disponible, se aplican las restricciones de enrutamiento basadas en la ubicación.

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

