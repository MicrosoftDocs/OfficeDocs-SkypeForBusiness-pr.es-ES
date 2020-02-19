---
title: 'Lync Server 2013: Ubicación del usuario'
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
ms.openlocfilehash: d18ef5092f0506951dd9b431c6a44945b87b7f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Ubicación del usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

El enrutamiento basado en ubicación aprovecha las mismas regiones de red, sitios y subredes que se definen en Lync Server usado por E9-1-1, CAC y media bypass para aplicar restricciones de enrutamiento de llamadas para evitar el desvío de peajes RTC. La ubicación de un usuario se determina en función de la subred IP de los puntos de conexión de Lync del usuario. Cada subred IP está asociada a un sitio de red, que se agrega a las regiones de red definidas por el administrador. El enrutamiento basado en ubicación se aplica en función del sitio de red del usuario.

Las reglas de enrutamiento basadas en ubicación se aplican por sitio de red, lo que significa que se aplicará un conjunto determinado de reglas a todos los extremos habilitados para el enrutamiento basado en ubicación que se encuentran en el mismo sitio de red. Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.

Las directivas de enrutamiento de voz se pueden definir en cada sitio de red para definir una puerta de enlace RTC determinada que deben usar todos los usuarios ubicados en el sitio de red para llamar a números de teléfono RTC. Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la Directiva de voz del usuario cuando el usuario se encuentre en un sitio de red habilitado para el enrutamiento basado en ubicación y impedirá el enrutamiento de llamadas a través de otras puertas de enlace RTC que estén habilitadas para Enrutamiento basado en ubicación. Cuando un usuario de Lync coloca una llamada RTC, la Directiva de voz del usuario determina si el usuario puede tener autorización para realizar la llamada. Si la Directiva de voz del usuario permite al usuario realizar la llamada, el enrutamiento basado en ubicación determina la puerta de enlace RTC de la que debe salir la llamada. El enrutamiento basado en ubicación realiza esta determinación en función de la ubicación del usuario.

Una ubicación de usuario se puede clasificar de las siguientes maneras:

  - El usuario se encuentra en un sitio de red conocido habilitado para el enrutamiento basado en ubicación y su número de DID (marcado interno directo) termina en una puerta de enlace RTC situada en el mismo sitio de red (por ejemplo, Office). El enrutamiento de las llamadas salientes será a través de la Directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario se enrutan a los extremos que se encuentran en el mismo sitio de red que la puerta de enlace RTC.

  - El usuario se encuentra en un sitio de red conocido que se encuentra en diferente del sitio de red donde se encuentra la puerta de enlace RTC. (es decir, el usuario ha viajado a otra oficina corporativa). El enrutamiento de las llamadas salientes estará usando la Directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario no se enrutarán a los extremos ubicados en sitios diferentes de la puerta de enlace RTC para evitar que se omitan los peajes RTC.

  - Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Lync Server, el enrutamiento de las llamadas salientes se basará en la Directiva de voz asignada al usuario a las puertas de enlace RTC no enlazadas con las restricciones de enrutamiento basadas en la ubicación. Las llamadas RTC entrantes no se enrutarán a los extremos ubicados en sitios de red desconocidos para evitar que se omitan los peajes RTC.

<div>

## <a name="see-also"></a>Vea también


[Guía para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

