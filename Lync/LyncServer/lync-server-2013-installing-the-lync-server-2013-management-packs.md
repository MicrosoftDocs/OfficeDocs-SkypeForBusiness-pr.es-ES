---
title: 'Lync Server 2013: instalación de los paquetes de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ff5b636c4cb2eaea2b3f7caa5681a26a8a59dc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534817"
---
# <a name="installing-the-lync-server-2013-management-packs"></a>Instalación de los paquetes de administración de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Por sí sola, System Center Operations Manager tiene la capacidad de supervisar solo una pequeña parte del sistema operativo Windows. Sin embargo, puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración, el software que determina qué elementos puede supervisar System Center Operations Manager, incluido cómo se deben supervisar esos elementos y cómo se deben desencadenar y notificar las alertas. Microsoft Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes capacidades:

  - El componente y el módulo de administración de usuarios (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en registros de eventos, registrados por los contadores de rendimiento o registrados en las bases de datos de registros de detalles de llamadas (CDR) o de calidad de la experiencia (QoE). Para los problemas críticos, System Center Operations Manager se puede configurar para que notifique inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o servicio de mensajes cortos (SMS). SMS es la tecnología que se usa para enviar mensajes de texto entre dispositivos móviles.
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea configuración de la notificación en la biblioteca de TechNet en <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> .

    
    </div>

  - El paquete de supervisión activo (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva los componentes clave de Lync Server como, por ejemplo, el inicio de sesión en el sistema, el intercambio de mensajes instantáneos o la realización de llamadas a un teléfono ubicado en la red telefónica conmutada (RTC). Estas pruebas se llevan a cabo con los cmdlets de transacciones sintéticas de Lync Server. Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba. Si esta conversación de mensajería simulada tiene errores, se genera una alerta.

Los dos módulos de administración que se incluyen en Lync Server 2013 incluyen un gran número de mejoras a través de los paquetes de administración que se usan con Microsoft Lync Server 2010. Por ejemplo, el módulo de administración de componentes de Lync Server 2013 no está limitado a la supervisión del propio Lync Server. Además de supervisar los registros de eventos y los contadores de rendimiento de Lync Server, el módulo de administración de componentes también puede realizar un seguimiento del rendimiento y emitir alertas para elementos cruciales, como:

  - **Internet Information Services (IIS)**     Se emitirán alertas si Internet Information Services se desconecta. Esto es importante porque los servicios Web de Lync Server se basan en IIS.

  - **Uso**     del proceso Las alertas se emitirán si los recursos del sistema (como la memoria disponible) comienzan a ejecutarse en un nivel bajo. Estas alertas se emitirán incluso si Lync Server no es responsable del uso elevado del sistema.

  - Eventos de error del **equipo**     Las alertas se emitirán en caso de un problema de hardware o software que amenace la viabilidad de un servidor. Por ejemplo, se notificará a los administradores de Lync Server si un servidor parece estar en peligro de experimentar un error de disco duro.

En los nuevos módulos de administración también se ha mejorado la creación de informes. Los nuevos informes para Lync Server 2013 incluyen:

  - Informe de disponibilidad **de escenario de principio a fin**     Este informe detalla la disponibilidad o el tiempo activo para los servicios clave de Lync Server, como el registro o la presencia.

  - **Informe**     de capacidad Mediante la información del contador de rendimiento, este informe muestra las tendencias de los componentes del sistema, como la disponibilidad de la memoria y el uso del procesador.

  - **Informe**     de componentes Este informe enumera los principales generadores de alertas agrupados por el componente de Lync Server.

Además de estos informes prediseñados, los paquetes de administración de Lync Server 2013 notifican automáticamente las alertas para la confiabilidad de las llamadas (métricas que miden el registro detallado de llamadas) y los Estados de la QoE (métricas medidas por calidad de la experiencia). Si ha habilitado el registro detallado de llamadas, puede revisar las alertas de confiabilidad de llamadas completando el siguiente procedimiento desde la consola de System Center Operations Manager:

  - Expanda **Supervisión**, **Estado de Microsoft Lync Server 2013** y **Confiabilidad de llamadas y calidad de medios**, y haga clic en **Confiabilidad de llamadas**.

Para ver las alertas de calidad de la experiencia, complete este procedimiento desde la consola de System Center Operations Manager:

  - Expanda **Supervisión**, **Estado de Microsoft Lync Server 2013**, **Confiabilidad de llamadas y calidad de medios** y **Calidad de medios**.

Los paquetes de administración de Lync Server 2013 ahora usan la detección en el nivel de equipo en lugar del mecanismo de detección central usado en Microsoft Lync Server 2010. Esto significa que cada agente de System Center se Descubre a sí mismo e informa de su existencia al servidor de administración central. El uso de la detección en el nivel de máquina simplifica la administración de la infraestructura de System Center y también permite que coexistan diferentes versiones de los paquetes de administración de Lync Server (por ejemplo, los módulos de administración de Lync Server 2010 y los paquetes de administración de Lync Server 2013).

</div>

<span> </span>

</div>

</div>

</div>

