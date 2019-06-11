---
title: 'Lync Server 2013: instalación de los módulos de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Instalar los módulos de administración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Por sí solo, System Center Operations Manager tiene la capacidad de supervisar solo una pequeña parte del sistema operativo Windows. Sin embargo, puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración, software que determina los elementos que System Center Operations Manager puede supervisar, incluido cómo se deben supervisar esos elementos y cómo deberían ser las alertas. desencadenado y notificado. Microsoft Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes características:

  - El componente y el paquete de administración de usuario (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o la calidad de la experiencia (QoE). bases. En el caso de problemas críticos, System Center Operations Manager se puede configurar para que notifiquen inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o mensajes SMS. SMS es la tecnología que se usa para enviar mensajes de texto desde un dispositivo móvil a otro.
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre la configuración de notificaciones de Operations Manager, vea configurar <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>notificaciones en la biblioteca de TechNet en.

    
    </div>

  - El paquete de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva componentes de Lync Server clave, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en el teléfono conmutado público. red (RTC). Estas pruebas se realizan mediante los cmdlets de transacciones sintéticas de Lync Server. Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba. Si se produce un error en esta conversación de mensajería simulada, se generará una alerta.

Los dos módulos de administración incluidos en Lync Server 2013 incluyen un gran número de mejoras en los paquetes de administración que se usan con Microsoft Lync Server 2010. Por ejemplo, el módulo de administración de componentes de Lync Server 2013 no se limita a supervisar el servidor de Lync en sí. Además de supervisar los registros de eventos y los contadores de rendimiento de Lync Server, el módulo de administración de componentes también puede realizar un seguimiento del rendimiento de elementos esenciales, como por ejemplo:

  - **Las alertas de servicios de Internet Information Server (IIS)**   se emitirán si servicios de Internet Information Server se desconecta. Esto es importante porque los servicios Web de Lync Server dependen de IIS.

  - ****   Las alertas de uso de procesos se emitirán si los recursos del sistema (como la memoria disponible) comienzan a agotarse. Estas alertas se emitirán incluso si Lync Server no es responsable del uso elevado del sistema.

  - ****   Las alertas de eventos de error de equipo se emitirán en caso de un problema de hardware o software que amenace la viabilidad de un servidor. Por ejemplo, los administradores de Lync Server recibirán una notificación si un servidor parece estar en peligro de experimentar un error en el disco duro.

Los nuevos paquetes de administración también ofrecen informes mejorados. Los nuevos informes para Lync Server 2013 incluyen:

  - **Informe de disponibilidad de escenario de principio a fin**   este informe detalla la disponibilidad y el tiempo de actividad de los servicios clave de Lync Server, como el registro o la presencia.

  - **Informe de capacidad**   con información de contador de rendimiento, este informe muestra tendencias de componentes del sistema, como la disponibilidad de memoria y el uso del procesador.

  - **Informe de componente**   este informe enumera los principales generadores de alertas agrupados por el componente Lync Server.

Además de estos informes prediseñados, los módulos de administración para Lync Server 2013 automáticamente notifican las alertas de confiabilidad de llamadas (métricas medidas por la grabación de detalles de llamadas) y los Estados de QoE (métricas medidas según la calidad de la experiencia). Si ha habilitado la grabación de detalles de llamadas, puede revisar las alertas de confiabilidad de llamadas completando el siguiente procedimiento de la consola de System Center Operations Manager:

  - Expanda **supervisión**, expanda **Estado 2013 de Microsoft Lync Server**, expanda **fiabilidad y calidad multimedia**y, después, haga clic en confiabilidad de la **llamada**.

Para ver las alertas de calidad de la experiencia, complete este procedimiento desde la consola de System Center Operations Manager:

  - Expanda **supervisión**, expanda **Estado de Microsoft Lync Server 2013**, expanda **fiabilidad y calidad multimedia**y, después, expanda **calidad de multimedia**.

Los módulos de administración para Lync Server 2013 ahora usan la detección a nivel de equipo en lugar del mecanismo de detección central usado en Microsoft Lync Server 2010. Esto significa que cada agente de System Center se descubre por sí mismo e informa de su existencia en el servidor de administración central. El uso de detección en el nivel de equipo simplifica la administración de la infraestructura de System Center y también permite el uso de diferentes versiones de los paquetes de administración de Lync Server (por ejemplo, módulos de administración para Lync Server 2010 y paquetes de administración para Lync Server 2013) para existi.

</div>

<span> </span>

</div>

</div>

</div>

