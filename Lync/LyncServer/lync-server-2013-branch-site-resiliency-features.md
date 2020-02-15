---
title: 'Lync Server 2013: características de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5f477bcb5620112789a338339b6ca00bf9c3c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Características de resistencia de sitios de sucursal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-10_

Al proporcionar resistencia a las sucursales, si se produce un error en la conexión WAN de una sucursal a un sitio central o si no se puede alcanzar el sitio central, las siguientes características de voz deberían seguir disponibles:

<div>


  - Llamadas de red telefónica conmutada (RTC) entrantes y realizadas.

  - Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes

  - Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.

  - Mensajería instantánea entre dos participantes

  - Desvío de llamadas, llamadas simultáneas a extremos, delegación de llamadas y servicios de llamada de equipo, pero solo si el delegador y el delegado (por ejemplo, un encargado y su administrador) o todos los miembros del equipo están configurados en el mismo sitio

  - Registros de detalles de las llamadas (CDR)

  - Conferencias de acceso telefónico local RTC con operador automático de conferencia

  - Capacidades de correo de voz, si configura la configuración de reenrutamiento del correo de voz. (Para obtener más información, consulte [requisitos de resistencia de sitios de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).

  - Autorización y autenticación de usuarios

Las siguientes características solo estarán disponibles si la solución de resistencia es una implementación de Lync Server a escala completa en el sitio de sucursal:

  - Conferencia A/V, web y MI

  - Enrutamiento basado en presencia y No molestar (DND) (con el que se evita que las llamadas suenen en extensiones con DND activado)

  - Actualización de la configuración del desvío de llamadas

  - Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

  - Aprovisionamiento de nuevos teléfonos y clientes, pero solo si los servicios de dominio de Active Directory están presentes en el sitio de sucursal.

  - 9-1-1 mejorado (E9-1-1)
    
    Si se ha implementado E9-1-1 y el tronco SIP en el sitio central no está disponible porque el vínculo WAN está inactivo, la aplicación de sucursal con funciones de supervivencia enrutará las llamadas de E9-1-1 a la puerta de enlace de sucursal local. Para habilitar esta característica, las directivas de voz de los usuarios de las sucursales deben enrutar las llamadas a la puerta de enlace local en caso de error de WAN.

<div>


> [!NOTE]  
> SBA (sucursal con funciones de supervivencia) no es compatible con XMPP. Los usuarios hospedados en una configuración de SBA no podrán enviar mensajes instantáneos ni ver presencia con contactos XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

