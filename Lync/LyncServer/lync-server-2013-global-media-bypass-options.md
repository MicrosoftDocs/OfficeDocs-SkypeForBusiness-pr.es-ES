---
title: 'Lync Server 2013: opciones globales de desvío de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96c97301221e50873ab53dc06452721c74ed6627
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Opciones de omisión de medios globales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

<div>


> [!NOTE]  
> En este tema se supone que ya se ha configurado un desvío de medios para los troncos a un interlocutor (una puerta de enlace de red telefónica conmutada (RTC), un IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet) para un sitio o servicio específico para que desea que los medios omitan el servidor de mediación.



</div>

Además de habilitar el desvío de medios para conexiones de tronco individuales asociadas con un par, también debe habilitar la omisión de medios globalmente. La configuración de desvío de medios globales puede especificar que se intente siempre una omisión de medios para las llamadas a la RTC o que la omisión de medios se emplee mediante la asignación de subredes a sitios de red y regiones de red, de manera similar a lo que hace el control de admisión de llamadas, otro característica de voz avanzada. Cuando se habilitan tanto el desvío de medios como el control de admisión de llamadas, la región de red, el sitio de red y la información de subred especificados para el control de admisión de llamadas se usan automáticamente al determinar si se debe emplear una omisión de medios. Esto significa que no puede especificar que el desvío de medios se intente siempre para las llamadas a la RTC cuando el control de admisión de llamadas esté habilitado.

En este tema se describe cómo usar el panel de control de Lync Server y el shell de administración de Lync Server a la vez que se configura la configuración de omisión de medios globales.

<div>


> [!NOTE]  
> Cuando se usan estos pasos para configurar el desvío de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP). En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse el desvío de medios en la llamada. La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Pasos siguientes: Elegir la configuración de desvío de medios global

Una vez habilitado el desvío de medios en las conexión de tronco a un nivel de los sitios o servicios especificados, haga uso del siguiente contenido para cualquiera de los siguientes cometidos:

  - Habilite siempre la omisión de medios, como se describe en [Configure media bypass in Lync Server 2013 para omitir siempre el servidor de mediación](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - O bien, configure la omisión de medios para usar la información de sitio y región, como se describe en [configurar la configuración global de desvío de medios en Lync Server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Consulta también


[Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

