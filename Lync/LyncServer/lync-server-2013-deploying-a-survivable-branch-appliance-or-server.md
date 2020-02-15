---
title: 'Lync Server 2013: implementación de una aplicación o un servidor de sucursal con funciones de supervivencia'
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
ms.openlocfilehash: 445df692041e24f8a4e134836ea9f6a63561a2ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-10_

Resistente Enterprise Voice hace referencia a la resistencia de los sitios de sucursal, es decir, a la capacidad de proporcionar un servicio de telefonía IP empresarial continuo a los usuarios de sitios de sucursal en el caso de que el vínculo al sitio central deje de estar disponible.

Para sitios de sucursal pequeños y medianos (sitios de sucursal con 25 a 1.000 usuarios), se recomienda implementar una aplicación de sucursal con funciones de supervivencia, que finalizará las llamadas de red telefónica conmutada (RTC) mediante la puerta de enlace RTC integrada o un tronco SIP a un teléfono. proveedor de servicios. Una aplicación de sucursal con funciones de supervivencia es un dispositivo de terceros que incluye un servidor blade que ejecuta el sistema operativo Windows Server 2008 R2, el registrador de Lync Server 2013, el software de servidor de mediación y una puerta de enlace RTC, todo en un solo chasis de dispositivo.

Para los sitios de sucursal con 1.000 a 5.000 y ninguna WAN resistente, se recomienda conectar un servidor de sucursal con funciones de supervivencia a una puerta de enlace RTC o a un tronco SIP a un proveedor de servicios telefónicos. Un servidor de sucursal con funciones de supervivencia es un equipo basado en Windows Server que tiene el registrador y el software de servidor de mediación instalado.

<div>


> [!NOTE]  
> Para los sitios de sucursal con más de 5.000 usuarios y administradores de Lync Server dedicados, se recomienda una implementación completa de Lync Server 2013, independiente de la del sitio central.<BR>Para obtener más información sobre cómo elegir la mejor solución de resistencia para los sitios de sucursal de la organización, incluidos los requisitos previos y las consideraciones de planeación, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site Resiliency Requirements for Lync Server 2013</A> en la documentación referente a la planeación.



</div>

<div>


> [!NOTE]  
> Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas de sitio central de Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Implementar una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Apéndices: servidores y aplicaciones de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

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

