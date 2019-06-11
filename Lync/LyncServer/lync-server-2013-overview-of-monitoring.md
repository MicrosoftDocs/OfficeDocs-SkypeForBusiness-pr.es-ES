---
title: 'Lync Server 2013: información general sobre la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Información general de la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

En Microsoft Lync Server 2013, la supervisión se usa para recopilar información de uso y datos de la calidad de la experiencia (QoE) sobre las sesiones de comunicación en las que participan los usuarios. Una sesión es un término genérico que cubre la conexión de un usuario a:

  - Una conferencia

  - Modalidad de conferencia (como audio/vídeo o uso compartido de aplicaciones)

  - Otro usuario a través de una conversación punto a punto, como un mensaje instantáneo o una llamada de audio

<div>


> [!NOTE]  
> Lync Server 2013 realiza un seguimiento de la información sobre cada sesión: quién llamó a quién; los puntos de conexión que se usaron en la sesión; la duración de la sesión es la última. Cuál fue la calidad percibida de la sesión; y así sucesivamente. Sin embargo, Lync Server no graba y almacena la propia llamada real. Esto incluye también sesiones de mensajería instantánea: aunque Lync Server registra información sobre las sesiones de mensajería instantánea, no mantiene un registro de todos los mensajes instantáneos que se enviaron durante la sesión.



</div>

La información de detalles de la llamada recopilada por Lync Server puede utilizarse para cualquier cantidad de usos, entre los que se incluyen:

  - Rentabilidad **de la inversión**. Los administradores pueden comparar los datos de uso recopilados por el servidor de supervisión con datos similares recopilados para su sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Lync Server.

  - **Administración del inventario de dispositivos**. La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos en uso que necesitan ser reemplazados, así como identificar dispositivos caros que no parecen usarse.

  - Servicio de asistencia. La solución de problemas de datos permite a los ingenieros de soporte determinar por qué falla la llamada de un usuario y hacerlo sin tener que recopilar registros del lado del servidor o del cliente. Esta información puede ser accesible y comprensible para el personal de soporte técnico que no tiene un profundo conocimiento técnico de Microsoft Lync 2013 y Lync Server 2013.

  - **Solución de problemas del sistema**. Los administradores pueden detectar problemas importantes que pueden impedir que los usuarios finales lleven a cabo tareas básicas, como unirse a una conferencia, realizar una llamada o enviar un mensaje instantáneo.

Además de esta información básica sobre llamadas, el servidor de supervisión también proporciona un mecanismo que permite que los puntos de conexión SIP (como Lync 2013) proporcionen información de solución de problemas a la que el servidor no tendría acceso de otra manera:

  - **Métricas multimedia que afectan**a la calidad. Estas métricas se ocupan de la transmisión real de la llamada; es decir, proporcionan un tipo de registro de viaje a medida que la llamada viaja por la red. Estas métricas (que incluyen factores como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) proporcionan información sobre lo que sucedió con la llamada desde el momento en que llegó hasta el momento en que llegó al punto final de la otra persona.

  - **Problemas notificados al usuario final**. Estas métricas incluyen notificaciones de mala calidad que Lync 2013 presenta a los usuarios finales en casos en los que están demasiado lejos de un micrófono, hablan demasiado de forma suave, tienen una mala conexión de red o experimentan una mala calidad porque otro programa del equipo está consumir los recursos disponibles.

  - **Información del entorno**. Estas métricas detallan los factores de calidad de la llamada, como el tipo de micrófono y altavoces que se usan, si el usuario se conecta a través de una conexión VPN y si tiene una conexión inalámbrica.

Al final de cada llamada, los extremos conformes con SIP transmiten automáticamente esta información al servidor front-end que facilita la llamada. No tiene que hacer nada para obtener puntos de conexión para transmitir esa información; ese comportamiento está integrado en el protocolo SIP. Sin embargo, si desea recopilar y almacenar esa información, tendrá que instalar y habilitar la supervisión. Si instala y habilita la supervisión, la información de la llamada se recopila por parte de los agentes que se ejecutan en el servidor front-end y lo retransmiten a un par de bases de datos de SQL Server.

Tenga en cuenta que el proceso de instalación y configuración de la supervisión se ha simplificado en Lync Server 2013. En versiones anteriores del software, la supervisión requería una función de servidor de supervisión independiente, que normalmente significaba un equipo independiente reservado para su uso como servidor de supervisión. En Lync Server 2013, sin embargo, se eliminó la función de servidor de supervisión. En su lugar, el servicio de supervisión (en forma de "agentes de recopilación de datos unificados") se ha colocado en todos los servidores front-end. Esto tiene al menos dos beneficios principales. Collocation del servicio de supervisión:

  - Disminuye el número de roles de servidor necesarios al implementar Lync Server 2013. Disminuir la función de servidor de supervisión también ayuda a reducir los costos al eliminar la necesidad de mantener servidores dedicados para la supervisión.

  - Reduce la complejidad de la configuración y la administración de Lync Server 2013. Al collocating los servicios de supervisión en cada servidor front-end que ya no necesita para instalar, configurar y administrar la función de servidor de supervisión.

Para obtener más información, vea el tema sobre la [implementación de la supervisión en Lync server 2013](lync-server-2013-deploying-monitoring.md) en la guía de implementación de lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

