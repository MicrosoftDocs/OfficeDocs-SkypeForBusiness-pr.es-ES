---
title: 'Lync Server 2013: Implementar una aplicación o servidor de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-10_

Resiliente Enterprise Voice hace referencia a la resistencia a sitios de sucursales, es decir, la capacidad de ofrecer un servicio de telefonía empresarial continua a los usuarios de sucursales en caso de que el vínculo al sitio central deje de estar disponible.

En el caso de sitios de sucursales pequeños y de tamaño mediano (sitios de sucursales con 25 a 1.000 usuarios), recomendamos implementar una aplicación de rama superviviente, que terminará las llamadas de la red telefónica conmutada (RTC) usando su puerta de enlace RTC integrada o un tronco SIP a un teléfono. proveedor de servicios. Un equipo de rama con la supervivencia es un dispositivo de terceros que incluye un servidor blade que ejecuta el sistema operativo Windows Server 2008 R2, el registrador de Lync Server 2013, el software de servidor de mediación y una puerta de enlace RTC, todo en un solo chasis de dispositivo.

En el caso de sitios de sucursales con 1.000 a usuarios de 5.000 y una WAN resistente, recomendamos que se conecte un servidor de sucursal con la supervivencia a una puerta de enlace PSTN o a un tronco SIP a un proveedor de servicios telefónicos. Un servidor de sucursal con la supervivencia es un equipo basado en Windows Server en el que se ha instalado el software de servidor de registro y mediación.

<div>


> [!NOTE]  
> Para los sitios de sucursales con más de 5.000 usuarios y administradores de Lync Server dedicados, recomendamos una implementación completa de Lync Server 2013, independiente de la del sitio central.<BR>Para obtener más información sobre cómo elegir la mejor solución de resistencia para los sitios de sucursales de su organización, incluidos los requisitos previos y las consideraciones de planeación, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resistencia de sitio de sucursal para Lync Server 2013</A> en la documentación de planeación.



</div>

<div>


> [!NOTE]  
> Los usuarios que estén alojados en un equipo con la aplicación de Lync Server superviviente no pueden crear nuevos salones de chat o ver la tarjeta de la sala de las habitaciones existentes.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013 - Tarea en el sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configuración de usuarios para la resistencia del sitio de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Apéndices: Servidores y aplicaciones de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

