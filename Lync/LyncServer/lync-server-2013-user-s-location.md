---
title: 'Lync Server 2013: Ubicación del usuario'
description: 'Lync Server 2013: Ubicación del usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561216"
---
# <a name="users-location-in-lync-server-2013"></a>Ubicación del usuario en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento de Location-Based aprovecha las mismas regiones de red, sitios y subredes que se definen en Lync Server usado por E9-1-1, CAC y la omisión de medios para aplicar restricciones de enrutamiento de llamadas para evitar el desvío de peajes RTC. La ubicación de un usuario se determina en función de la subred IP de los puntos de conexión de Lync del usuario. Cada subred IP está asociada a un sitio de red, que se agrega a las regiones de red definidas por el administrador. El enrutamiento de Location-Based se aplica en función del sitio de red del usuario.

Location-Based reglas de enrutamiento se aplican por sitio de red, lo que significa que se aplicará un conjunto determinado de reglas a todos los extremos habilitados para Location-Based enrutamiento que se encuentran en el mismo sitio de red. Los administradores pueden aplicar Location-Based enrutamiento a sitios de red que lo necesiten.

Las directivas de enrutamiento de voz se pueden definir en cada sitio de red para definir una puerta de enlace RTC determinada que deben usar todos los usuarios ubicados en el sitio de red para llamar a números de teléfono RTC. Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la Directiva de voz del usuario cuando el usuario se encuentre en un sitio de red habilitado para Location-Based enrutamiento y impedirá el enrutamiento de llamadas a través de otras puertas de enlace RTC habilitadas para Location-Based enrutamiento. Cuando un usuario de Lync coloca una llamada RTC, la Directiva de voz del usuario determina si el usuario puede tener autorización para realizar la llamada. Si la Directiva de voz del usuario permite al usuario realizar la llamada, Location-Based enrutamiento determina la puerta de enlace RTC de la que debe salir la llamada. El enrutamiento de Location-Based realiza esta determinación en función de la ubicación del usuario.

Una ubicación de usuario se puede clasificar de las siguientes maneras:

  - El usuario se encuentra en un sitio de red conocido habilitado para Location-Based enrutamiento y su número de ha finalizado (marcado directo) termina en una puerta de enlace RTC situada en el mismo sitio de red (por ejemplo, Office). El enrutamiento de las llamadas salientes será a través de la Directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario se enrutan a los extremos que se encuentran en el mismo sitio de red que la puerta de enlace RTC.

  - El usuario se encuentra en un sitio de red conocido que se encuentra en diferente del sitio de red donde se encuentra la puerta de enlace RTC. (es decir, el usuario ha viajado a otra oficina corporativa). El enrutamiento de las llamadas salientes estará usando la Directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario no se enrutarán a los extremos ubicados en sitios diferentes de la puerta de enlace RTC para evitar que se omitan los peajes RTC.

  - Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Lync Server, el enrutamiento de las llamadas salientes se basará en la Directiva de voz asignada al usuario a las puertas de enlace RTC no enlazadas a las restricciones de enrutamiento Location-Based. Las llamadas RTC entrantes no se enrutarán a los extremos ubicados en sitios de red desconocidos para evitar que se omitan los peajes RTC.

<div>

## <a name="see-also"></a>Consulte también


[Guía para el enrutamiento de Location-Based en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

