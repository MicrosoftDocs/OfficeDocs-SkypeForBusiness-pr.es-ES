---
title: 'Lync Server 2013: Consideraciones técnicas para el enrutamiento basado en ubicación'
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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Consideraciones técnicas para el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Al planear el enrutamiento basado en la ubicación, debe considerar el impacto en los siguientes escenarios.

<div>

## <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del repositorio principal a un grupo de copia de seguridad, así como al restaurar operaciones normales en el repositorio principal, el enrutamiento basado en la ubicación se mantiene en todo momento durante un procedimiento de recuperación ante desastres.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

La configuración del enrutamiento basado en la ubicación afecta al planeamiento de la ubicación en la que se implementan las puertas de enlace asociadas a los dispositivos de las sucursales que son revivientes. La puerta de enlace asociada a su SBA debe estar ubicada en el mismo sitio de red que su equipo de sucursal con la supervivencia; de lo contrario, los usuarios alojados en su equipo de sucursal con su supervivencia no podrán realizar llamadas salientes si el enrutamiento basado en la ubicación está configurado. Cuando la conexión WAN entre el equipo de la sucursal y el sitio central está inactivo, se exige la aplicación de las restricciones de enrutamiento basadas en la ubicación.

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

