---
title: 'Lync Server 2013: diseño del tronco del SIP para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Diseño del tronco del SIP para E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Lync Server usa los troncos SIP para conectar una llamada de emergencia con el proveedor de servicios E9-1-1. Puedes configurar troncos SIP del servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Pero, si el vínculo WAN entre el sitio del autor de la llamada y el sitio que aloja el tronco SIP del servicio de emergencia no está disponible, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz del usuario que redirigirá la llamada al ECRC a través de la puerta de enlace de la red telefónica conmutada (RTC) local. Lo mismo sucede si se aplican los límites de las llamadas simultáneas del servicio de control de admisión de llamadas.

<div>


> [!NOTE]  
> Hay dos formas de implementar un tronco de SIP en un entorno de Lync Server: 
> <UL>
> <LI>
> <P>Use servidores de mediación multitarjeta que usen sus interfaces de enrutamiento público con el exterior para comunicarse con el proveedor de troncal de SIP.</P>
> <LI>
> <P>Use un controlador de borde de sesión (SBC) local para proporcionar un punto de delimitación seguro entre los servidores de mediación y los servicios del proveedor de troncal del SIP.</P></LI></UL>Si eliges el último método, asegúrate de que el modelo y la marca del SBC que elijas estén certificado y admitan el paso de datos de ubicación del objeto de localización del formato de datos de información de presencia (PIDF-LO) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para obtener más información sobre SBCs certificado, consulte "Infrastructure Qualified for Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>" en.<BR>Los proveedores de servicios E9-1-1 proporcionan acceso a un par de SBCs por redundancia. Debe tomar varias decisiones en relación con la topología de servidor de mediación y la configuración de enrutamiento de llamadas. ¿Tratará tanto SBCs como pares iguales y usará el enrutamiento de operación por turnos para las llamadas entre ellos, o se designará un SBC como principal y el otro como secundario?



</div>

Para obtener detalles sobre la implementación de un tronco SIP en Lync Server, consulte [¿Cómo puedo implementar la Troncalización SIP en Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Las siguientes preguntas te ayudarán a decidir cómo implementar los troncos SIP para E9-1-1.

  - **¿Tendría que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**  
    Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que cambiarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerda que si vas a conectar con proveedores de servicios de emergencia en la red de Internet pública y necesitas garantizar la confidencialidad de las llamadas de emergencia, es necesario el cifrado IPSec.

<!-- end list -->

  - **¿Su implementación de E9-1-1 está diseñada para la tolerancia ante desastres?**  
    Como se trata de una solución de emergencia, la resistencia es importante. Implementar los servidores de mediación y los troncos SIP principales y secundarios en ubicaciones con tolerancia ante desastres. Es buena idea implementar el servidor de mediación principal más cercano a los usuarios que es compatible y enrutar las llamadas de conmutación por error a través del servidor de mediación secundaria (que se encuentra en una ubicación geográfica diferente).

<!-- end list -->

  - **¿Tendría que implementar un tronco SIP independiente para cada sucursal?**  
    Lync Server proporciona varias estrategias para controlar la resistencia de voz en sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o presionar las llamadas a la puerta de enlace local durante las interrupciones. Para obtener más información, consulte [Troncalización SIP de sitio de sucursal en Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**  
    Lync Server no maneja las llamadas de emergencia de ninguna otra forma. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) pueden afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o redirigir a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están redirigiendo las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se necesitan redirigir manualmente al ECRC.

</div>

<span> </span>

</div>

</div>

</div>

