---
title: 'Lync Server 2013: opciones de omisión de multimedia global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Opciones de omisión de multimedia global en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

<div>


> [!NOTE]  
> En este tema se supone que ya ha configurado la omisión de medios para cualquier conexión a un interlocutor (una puerta de enlace de red telefónica conmutada (RTC), una IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet) para un sitio o servicio específico para que quiere que los medios omitan el servidor de mediación.



</div>

Además de habilitar la omisión de medios para las conexiones de tronco individuales asociadas a un nivel, también deberá habilitar la omisión de medios de forma global. La configuración de la omisión de medios global puede establecer que se intente realizar siempre una omisión de medios de las llamadas a RTC, o bien que la omisión de medios se use con la asignación de subredes a sitios y regiones de red, algo similar a lo que lleva a cabo el control de admisión de llamadas, que es otra característica de voz avanzada. Cuando tanto la omisión de medios como el control de admisión de llamadas están habilitados, la información de región de red, sitio de red y subred especificada para el control de admisión de llamadas se usa automáticamente para determinar si ha de usarse o no la omisión de medios, lo cual quiere decir que no siempre se va a poder especificar que se intente omitir los medios a RTC siempre cuando el control de admisión de llamadas está habilitado.

En este tema se describe cómo usar el panel de control de Lync Server y el shell de administración de Lync Server juntos para configurar las opciones globales de omisión de medios.

<div>


> [!NOTE]  
> Cuando se usan estos pasos para configurar la omisión de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP). En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse la omisión de medios en la llamada. La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco. La omisión de elementos multimedia solo se admite con productos y versiones que se incluyen en el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Pasos siguientes: elegir la configuración de omisión de multimedia global

Después de habilitar la omisión de medios en las conexiones troncales a un interlocutor para determinados servicios o sitios, use el siguiente contenido para:

  - Habilite siempre la omisión de medios, como se describe en [configurar omisión de contenido multimedia en Lync Server 2013 para omitir siempre el servidor](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)de mediación.

  - También puede configurar la omisión de medios para usar la información del sitio y de la región, como se describe en [configurar la configuración global de omisión de contenido multimedia en Lync Server 2013 para usar la información de la región y el sitio](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Omisión de medios y servidor de mediación en Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

