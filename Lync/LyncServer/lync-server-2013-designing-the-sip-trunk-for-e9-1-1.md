---
title: 'Lync Server 2013: diseño del tronco SIP para E9-1-1'
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
ms.openlocfilehash: 920eecbdb456e3b643da9f935e2586dea7e6e165
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Diseño del tronco SIP para E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Lync Server usa troncos SIP para conectar una llamada de emergencia con el proveedor de servicios E9-1-1. Puede configurar un tronco SIP de servicio de emergencia para E9-1-1 en un sitio central, en varios sitios centrales o en cada sitio de sucursal. Sin embargo, si el vínculo WAN entre el sitio del autor de la llamada y el sitio que aloja el tronco SIP del servicio de emergencia no está disponible, una llamada realizada por un usuario en el sitio desconectado necesitará un registro de uso de teléfono especial en la directiva de voz de usuario que enrute la llamada al ECRC a través de la puerta de enlace de la red telefónica conmutada pública (RTC) local. Lo mismo sucede si se aplica un control de admisión de llamadas a la llamada.

<div>


> [!NOTE]  
> Hay dos formas de implementar un tronco SIP en un entorno de Lync Server: 
> <UL>
> <LI>
> <P>Use servidores de mediación multitarjeta que usen interfaces enrutadas públicamente dirigidas hacia el exterior para comunicarse con el proveedor de tronco SIP.</P>
> <LI>
> <P>Use un controlador de borde de sesión (SBC) local para proporcionar un punto de demarcación segura entre los servidores de mediación y los servicios del proveedor de tronco del SIP.</P></LI></UL>Si elige el último método, asegúrese de que el modelo y la marca SBC que elija admite el paso de datos de ubicación PIDF-LO (Presence Information Data Format Location Object, en inglés) como parte de su SIP INVITE. De lo contrario, las llamadas llegarán al proveedor de los servicios de emergencia sin información de su ubicación. Para obtener más información sobre los SBC certificados, consulte "infraestructura calificada para <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>Microsoft Lync" en.<BR>Los proveedores de servicios E9-1-1 proporcionan acceso a un par de SBC por redundancia. Debe tomar varias decisiones con respecto a la topología del servidor de mediación y la configuración de enrutamiento de llamadas. ¿Va a tratar ambos SBC como equivalentes y usar el enrutamiento Round Robin para las llamadas entre ellos, o se designe un SBC como principal y el otro como secundario?



</div>

Para obtener más información sobre cómo implementar un tronco SIP en Lync Server, vea [¿Cómo puedo implementar el enlace troncal SIP en Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Las siguientes preguntas le ayudarán a decidir cómo implementar troncos SIP para E9-1-1.

  - **¿Tendrá que implementar el tronco SIP a través de una conexión alquilada dedicada o de una conexión a Internet compartida?**  
    Es importante que las llamadas de emergencia conecten siempre. Una línea dedicada proporciona una conexión que no tendrá que reemplazarse por otro tráfico de la red y ofrece la posibilidad de implementar Calidad de servicio (QoS). Recuerde que si va a conectar con proveedores de servicios de emergencia en Internet público y debe garantizar la confidencialidad de las llamas de emergencia, es necesario el cifrado IPSec.

<!-- end list -->

  - **¿Su implementación de E9-1-1 está diseñada para la tolerancia ante desastres?**  
    Como se trata de una solución de emergencia, la resistencia es importante. Implementar los servidores de mediación principales y secundarios y los troncos SIP en las ubicaciones tolerantes a desastres. Es una buena idea implementar el servidor de mediación principal más cercano a los usuarios que es compatible y enrutar las llamadas de conmutación por error a través del servidor de mediación secundario (ubicado en una ubicación geográfica distinta).

<!-- end list -->

  - **¿Deberá implementar un tronco SIP independiente para cada sucursal?**  
    Lync Server ofrece varias estrategias para controlar la resistencia de voz en las sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o insertar llamadas en la puerta de enlace local durante las interrupciones. Para obtener más información, consulte [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **¿Está habilitado el servicio de control de admisión de llamadas (CAC)?**  
    Lync Server no administra las llamadas de emergencia de forma distinta a una llamada ordinaria. Por este motivo, la administración de ancho de banda o el servicio de control de admisión de llamadas (CAC) puede afectar de forma negativa a una configuración de E9-1-1. Las llamadas de emergencia se pueden bloquear o enrutar a la puerta de enlace RTC local si hay un CAC habilitado y se supera el límite configurado en un vínculo al que se están enrutando las llamadas de emergencia. Como se ha indicado antes en este tema, dichas llamadas no tendrán datos de ubicación y se deben enrutar manualmente al ECRC.

</div>

<span> </span>

</div>

</div>

</div>

