---
title: Sitios de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Sitios de Lync Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

En Lync Server, define los *sitios* de su red que contienen los componentes de Lync Server. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que los sitios de Lync Server son un concepto independiente de los sitios de los servicios de dominio de Active Directory y los sitios de Microsoft Exchange Server. Los sitios de Lync Server no necesitan corresponderse con los sitios de Active Directory.

<div>

## <a name="site-types"></a>Tipos de sitio

Cada sitio es un *sitio central*, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition, o un *sitio de sucursal*. Cada sitio de sucursal está asociado exactamente a un sitio central y los usuarios del sitio de la sucursal obtienen la mayor parte de la funcionalidad de Lync Server de los servidores del sitio central asociado.

Cada sitio de la sucursal contiene una de las siguientes opciones:

  - Un *dispositivo de rama con la supervivencia (SBA)*, que es un servidor blade estándar del sector con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server. El dispositivo de sucursal con la supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). El equipo de sucursales con la que es superviviente está diseñado para sucursales con entre 25 y 1000 usuarios.

  - Un *servidor de sucursal (SBS) con supervivencia*, que es un servidor que ejecuta Windows Server y que cumple con los requisitos de hardware especificados y que tiene instalado el software de servidor de mediación y registrador de Lync Server. Debe conectarse a una puerta de enlace PSTN o a un tronco SIP a un proveedor de servicios telefónicos. El servidor de sucursal con la supervivencia está diseñado para sucursales con usuarios de 1000 y 5000.

  - Una puerta de enlace RTC y, opcionalmente, un *servidor*de mediación. Para obtener más información sobre este y otros roles de servidor, vea [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).

Una sucursal con un vínculo de red de área extensa (WAN) resistente a un sitio central puede usar la tercera opción: una puerta de enlace RTC y, opcionalmente, un servidor de mediación. Los sitios de sucursales con vínculos menos resistentes deben usar un equipo de sucursal o un servidor de sucursal que sea reviviente y que ofrezcan resiliencia en momentos de errores de red de área extensa. Por ejemplo, en un sitio con una sucursal o un servidor de sucursal superviviente implementado, los usuarios pueden seguir realizando y recibiendo llamadas de voz empresariales si la WAN que conecta el sitio de la sucursal con el sitio central está desactivada. Para más información sobre la aplicación de sucursales con capacidad de supervivencia, servidor de sucursal y resistencia, consulte [planificación de la resistencia de voz empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación de planificación.

</div>

<div>

## <a name="site-topologies"></a>Topologías de sitios

La implementación debe incluir al menos un sitio central y puede incluir entre cero y muchos sitios de la sucursal. Cada sitio de sucursal está afiliado a un sitio central. El sitio central proporciona los servicios de Lync Server al sitio de la sucursal que no está hospedado localmente en el sitio de la sucursal, como la presencia y la Conferencia.

Si tiene varios sitios, puede emparejar los grupos de aplicaciones para el usuario en diferentes sitios para habilitar las capacidades de recuperación ante desastres. Para obtener más información, consulte [compatibilidad de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md)  
[Compatibilidad entre la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

