---
title: 'Lync Server 2013: Características de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e452dc297a79525b587d13aa58ed1e1270d41aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Características de resistencia de sitios de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-10_

Si proporciona resistencia al sitio de la sucursal, si se produce un error en la conexión WAN de un sitio de sucursal con un sitio central o si el sitio central no está accesible, las siguientes características de voz deben seguir estando disponibles:

<div>


  - Llamadas de red telefónica conmutada (RTC) entrantes y salientes

  - Llamadas empresariales entre usuarios en el mismo sitio y entre dos sitios diferentes

  - Manejo básico de llamadas, que incluye la llamada en espera, la recuperación y la transferencia

  - Mensajería instantánea de dos participantes

  - Desvío de llamadas, llamadas simultáneas a puntos de conexión, Delegación de llamadas y servicios de llamada de equipo, pero solo si el delegado y el delegado (por ejemplo, un administrador y el administrador del administrador) o todos los miembros del equipo están configurados en el mismo sitio

  - Registros de detalles de llamadas (CDRs)

  - Conferencias de acceso telefónico local RTC con operador automático de conferencia

  - Capacidades de correo de voz, si configura la configuración de redireccionamiento del correo de voz. (Para obtener información detallada, consulte [requisitos de resistencia de sitio de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).

  - Autenticación y autorización de usuarios

Las siguientes características solo estarán disponibles si la solución de resistencia es una implementación de Lync Server a escala completa en el sitio de la sucursal:

  - Mensajería instantánea, Web y conferencias A/V

  - Enrutamiento basado en presencia y no molestar (DND) (donde se impide que las llamadas suenen en extensiones que tienen la activada DND)

  - Actualización de la configuración del desvío de llamadas

  - Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

  - Aprovisionamiento de nuevos teléfonos y clientes, pero solo si los servicios de dominio de Active Directory están presentes en el sitio de la sucursal.

  - Enhanced 9-1-1 (E9-1-1)
    
    Si se implementa E9-1-1 y el tronco del SIP del sitio central no está disponible debido a que el vínculo WAN está desactivado, el equipo de la sucursal con la que es posible que se enruten las llamadas de E9-1 a la puerta de enlace local. Para habilitar esta característica, las directivas de voz de los usuarios de los sitios de sucursales deberían enrutar las llamadas a la puerta de enlace local en el caso de producirse un error de WAN.

<div>


> [!NOTE]  
> SBA (sucursal superviviente) no es compatible con XMPP. Los usuarios alojados en una configuración de SBA no podrán enviar mensajes instantáneos ni ver su presencia con contactos XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

