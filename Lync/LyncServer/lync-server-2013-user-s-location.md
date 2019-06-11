---
title: 'Lync Server 2013: Ubicación del usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Ubicación del usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento basado en la ubicación aprovecha las mismas regiones, sitios y subredes de la red que se definen en Lync Server usado por E9-1-1, CAC y media bypass para aplicar restricciones de enrutamiento de llamadas para evitar el bypass de llamadas RTC. La ubicación de un usuario viene determinada por la subred IP de los puntos de conexión de Lync del usuario. Cada subred IP está asociada a un sitio de red, y los sitios de red se agrupan en regiones de red definidas por el administrador. El enrutamiento basado en ubicación se aplica en función del sitio de red del usuario.

Las reglas de enrutamiento basadas en ubicación se aplican por sitio de red, lo que significa que se aplicará a todos los puntos de conexión que estén habilitados para el enrutamiento basado en la ubicación que se encuentra dentro del mismo sitio de red. Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.

Se pueden definir directivas de enrutamiento de voz en cada sitio de red, para que todos los usuarios ubicados en el sitio de red utilicen una puerta de enlace RTC concreta para llamar a números de teléfono de RTC. Dichas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la Directiva de voz del usuario cuando el usuario se encuentre en un sitio de red habilitado para el enrutamiento basado en la ubicación y evitará el enrutamiento de llamadas a través de otras puertas de enlace RTC habilitadas para Enrutamiento basado en la ubicación. Cuando un usuario de Lync realiza una llamada RTC, la Directiva de voz del usuario determina si el usuario puede tener autorización para realizar la llamada. Si la Directiva de voz del usuario permite al usuario realizar la llamada, el enrutamiento basado en la ubicación determina qué puerta de enlace RTC debe salir de la llamada. El enrutamiento basado en la ubicación realiza esta determinación en función de la ubicación del usuario.

La ubicación de un usuario se puede clasificar de las siguientes maneras:

  - El usuario se encuentra en un sitio de red conocido habilitado para enrutamiento basado en la ubicación y su número de ha finalizado (marcado directo) finaliza en una puerta de enlace RTC situada en el mismo sitio de red (es decir, Office). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario se redirigirán a los extremos ubicados en el mismo sitio de red que la puerta de enlace RTC.

  - El usuario está ubicado en un sitio de red conocido y diferente del sitio de red donde se encuentra la puerta de enlace RTC (es decir, el usuario viajó a otra oficina de la compañía). El enrutamiento de las llamadas salientes utilizará la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario no se redirigirán a los extremos ubicados en sitios diferentes del de la puerta de enlace RTC, para evitar que se omitan los números de pago de RTC.

  - Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Lync Server, el enrutamiento de las llamadas salientes se basará en la Directiva de voz asignada al usuario a las puertas de enlace RTC no enlazadas a las restricciones de enrutamiento basadas en la ubicación. Las llamadas de RTC entrantes no se redirigirán a los extremos ubicados en sitios de red desconocidos, para evitar que se omitan los números de pago de RTC.

<div>

## <a name="see-also"></a>Vea también


[Instrucciones para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

