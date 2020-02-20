---
title: 'Lync Server 2013: información general sobre la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d53d740af9cb0407b0309d858d4a1a85b3b976
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Información general sobre la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

En Microsoft Lync Server 2013, la supervisión se usa para recopilar información de uso y datos de calidad de la experiencia (QoE) sobre las sesiones de comunicación en las que participan los usuarios. Una sesión es un término genérico que cubre la conexión de un usuario a:

  - Conversación

  - Modalidad de conferencia (como audio/vídeo o uso compartido de aplicaciones)

  - Otro usuario a través de una conversación punto a punto, como la mensajería instantánea o una llamada de audio

<div>


> [!NOTE]  
> Lync Server 2013 realiza un seguimiento de la información sobre cada sesión: quién ha llamado quién; los puntos de conexión que se usaron en la sesión; la duración de la sesión finalizó por última vez; Cuál era la calidad percibida de la sesión; y así sucesivamente. Sin embargo, Lync Server no registra y almacena la propia llamada real. Esto incluye también sesiones de mensajería instantánea: aunque Lync Server registra información sobre las sesiones de mensajería instantánea, no mantiene un registro de los mensajes instantáneos que se enviaron durante la sesión.



</div>

La información de detalles de llamadas recopilada por Lync Server puede usarse para cualquier cantidad de usos, como:

  - **Retorno de la inversión (ROI)**. Los administradores pueden comparar los datos de uso recopilados por el servidor de supervisión con datos similares recopilados para el sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Lync Server.

  - **Administración del inventario de dispositivos**. La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos en uso que se deben reemplazar, así como identificar dispositivos caros que no parece que se usen en absoluto.

  - Servicio de asistencia. Los datos de solución de problemas permiten a los ingenieros de soporte técnico determinar por qué se ha producido un error en la llamada de un usuario y hacerlo sin tener que recopilar registros del servidor o del cliente. El personal de soporte técnico puede tener acceso a esta información y entenderla fácilmente que no tienen un profundo conocimiento técnico de Microsoft Lync 2013 y Lync Server 2013.

  - **Solución de problemas del sistema**. Permite a los administradores detectar los principales problemas que podrían impedir que los usuarios finales realicen tareas básicas, como unirse a una conferencia, establecer una llamada o enviar un mensaje instantáneo.

Además de esta información básica de llamadas, el servidor de supervisión también proporciona un mecanismo que permite que los extremos SIP (como Lync 2013) proporcionen información de solución de problemas que, de otro modo, el servidor no tendría acceso a:

  - **Métricas multimedia que afectan**a la calidad. Estas métricas tratan con la transmisión real de la propia llamada; es decir, proporcionan un tipo de registro de viajes a medida que los recorridos de llamadas a través de la red. Estas métricas (que incluyen aspectos como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) proporcionan información sobre lo que sucedió con la llamada desde el momento en que llegó el extremo hasta el momento en que llegó al punto de conexión de la otra persona.

  - **Problemas notificados al usuario final**. Estas métricas incluyen notificaciones de mala calidad que Lync 2013 presenta a los usuarios finales en los casos en los que están demasiado lejos de un micrófono, hablando demasiado en exceso, sin una conexión de red deficiente o con una calidad deficiente porque otro programa del equipo es consumo de los recursos disponibles.

  - **Información del entorno**. Estas métricas detallan los factores de calidad de las llamadas, como el tipo de micrófono y los altavoces que se usan, si el usuario está conectado a través de una conexión VPN y si el usuario está en una conexión inalámbrica.

Al final de cada llamada, los extremos compatibles con SIP transmiten automáticamente esta información al servidor front-end que facilita la llamada. No tiene que hacer nada para obtener los extremos para transmitir esa información; ese comportamiento se integra en el protocolo SIP. Sin embargo, si desea recopilar y almacenar esa información, debe instalar y habilitar la supervisión. Si instala y habilita la supervisión, la información de llamadas se recopila a través de los agentes que se ejecutan en el servidor front-end y los retransmite a un par de bases de datos de SQL Server.

Tenga en cuenta que el proceso de instalación y configuración de la supervisión se ha simplificado en Lync Server 2013. En versiones anteriores del software, la supervisión requería una función de servidor de supervisión independiente, que normalmente significaba un equipo independiente reservado para su uso como servidor de supervisión. Sin embargo, en Lync Server 2013, la función del servidor de supervisión se ha eliminado. En su lugar, el servicio de supervisión (en forma de "agentes de recopilación de datos unificados") se ha combinado en todos los servidores front-end. Esto tiene al menos dos beneficios principales. Combinación del servicio de supervisión:

  - Reduce el número de roles de servidor necesarios al implementar Lync Server 2013. La disminución de la función de servidor de supervisión también contribuye a reducir los costos al eliminar la necesidad de mantener servidores dedicados para la supervisión.

  - Reduce la complejidad de la instalación y administración de Lync Server 2013. Al combinar los servicios de supervisión en cada servidor front-end que ya no tiene para instalar, configurar y administrar el rol de servidor de supervisión.

Para obtener más información, consulte el tema [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) en la guía de implementación de lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

