---
title: 'Lync Server 2013: consideraciones técnicas para el enrutamiento Location-Based'
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
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536187"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Consideraciones técnicas sobre el enrutamiento Location-Based en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Al planear Location-Based el enrutamiento, debe tener en cuenta el impacto en los siguientes escenarios.

<div>

## <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del grupo principal a un grupo de copia de seguridad, así como cuando se restauran operaciones normales en el grupo principal, Location-Based el enrutamiento se aplica en todo momento durante un proceso de recuperación y desastre.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

La configuración del enrutamiento de Location-Based afecta a la planeación de la ubicación en la que se implementan las puertas de enlace asociadas a las aplicaciones de sucursal con funciones de supervivencia. La puerta de enlace asociada a SBA debe estar ubicada en el mismo sitio de red que la aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios hospedados en su aplicación de sucursal con funciones de supervivencia no podrán realizar llamadas salientes si se configura Location-Based enrutamiento. Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central no está disponible, se aplican Location-Based restricciones de enrutamiento.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación del enrutamiento de Location-Based en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

