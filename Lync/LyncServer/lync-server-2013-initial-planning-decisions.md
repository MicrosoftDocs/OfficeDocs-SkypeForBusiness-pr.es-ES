---
title: 'Lync Server 2013: Decisiones de planeación iniciales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Decisiones de planeación iniciales para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La primera parte del proceso de planeación es decidir qué cargas de trabajo y características principales de Lync Server desea para su organización.

1.  **¿Desea una implementación local o en línea?**    Lync Server admite ambos escenarios de implementación. Para obtener más información sobre cómo tomar esta decisión, consulte [decidir cómo implementar Lync Server 2013, que](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)aparece anteriormente en esta sección.

2.  **¿Desea una topología física o virtualizada?**    Lync Server admite todas las cargas de trabajo y roles de servidor en topologías físicas y virtualizadas. La capacidad de usuario y la escalabilidad pueden diferir entre las topologías físicas y virtuales. Para obtener más información, vea [Ejecutar Lync Server 2013 en servidores virtuales](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **La mensajería instantánea *(mi)* y la *presencia* siempre están habilitadas.**    En cualquier implementación de Lync Server, la mensajería instantánea (mi) y la carga de trabajo de presencia están instaladas y habilitadas de forma predeterminada. La mensajería instantánea permite que los usuarios se comuniquen con mensajes de texto en tiempo real y la presencia les permite ver el estado de otros usuarios de la red. El estado de presencia de un usuario proporciona información para ayudar a otros usuarios a decidir si deben intentar ponerse en contacto con el usuario y por qué lo hacen. Para obtener más información, consulte [planificación de servidores front-end, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) en la documentación de planeación.

4.  **¿Desea implementar cualquier modo de conferencia?**    Conferencias es otra de las características principales de Lync Server. Se admiten varios modos de conferencia. Puede elegir implementar todos los tipos de conferencia compatibles o solo algunos de ellos. Las *conferencias web* permiten a los usuarios ver un archivo, como un conjunto de diapositivas creado con el programa de gráficos de presentación de Microsoft PowerPoint, que se presenta. El *uso compartido de aplicaciones* permite a los usuarios compartir todo o parte de su escritorio en tiempo real. Con *conferencias a/V*, los usuarios pueden agregar audio (y posiblemente video) a sus conferencias y a las comunicaciones par a par. Las *conferencias de acceso telefónico local* permiten a los usuarios usar teléfonos RTC estándar para unirse a la parte de audio de las conferencias hospedadas en la organización. Para obtener más información, vea [planificación de conferencias en Lync Server 2013](lync-server-2013-planning-for-conferencing.md) en la documentación de planeación.
    
    En Lync Server 2013, si implementa conferencias web, también debe planear la integración con Office Web Apps Server para habilitar el uso compartido y la visualización de PowerPoint en reuniones. Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Si implementa conferencias A/V, también debe supervisar la calidad de audio de estas conferencias.**    Muchos factores afectan a la calidad de audio y vídeo de las conferencias A/V de Lync Server. Al usar la supervisión, puede supervisar la calidad de A/V de las llamadas y las conferencias. Puede detectar problemas que afectan a la calidad de los medios y asegurarse de que los usuarios tengan la mejor experiencia multimedia posible. Para obtener más información, vea [planear la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **¿Desea una alta disponibilidad para sus servidores de mensajería instantánea, presencia y conferencias?**    Si solo tiene un servidor en un sitio que proporciona características de conferencia, presencia y mensajería instantánea, la productividad de los usuarios se verá afectada en gran medida si el servidor deja de funcionar. Al implementar un *Grupo* de Enterprise Edition de al menos tres servidores para estas funciones, permite que Lync Server siga funcionando con todas estas características intactas incluso si un servidor no está disponible.
    
    Otra opción para organizaciones con 5000 o menos usuarios que desean una alta disponibilidad es implementar dos servidores que ejecuten Lync Server Standard Edition y emparejar estos servidores. Para obtener más información, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **¿Desea opciones de recuperación ante desastres?**    Si tiene dos centros de recursos y desea opciones de recuperación ante desastres para permitir que los usuarios sigan trabajando en caso de que todos o muchos servidores de un centro de trabajo se desconecten, puede implementar los servidores teniendo en cuenta la recuperación ante desastres. Para esta implementación, empareja un grupo de servidores en un centro de recursos con un grupo correspondiente en otro centro de recursos. Si se interrumpe un centro de proceso, el otro grupo del par puede atender a los usuarios de ambos grupos con una interrupción mínima de los servicios. Para obtener más información, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **¿Desea permitir que los usuarios se comuniquen y colaboren con usuarios externos?**    Habilitar la comunicación y colaboración con usuarios externos puede aumentar el retorno de la inversión en Lync Server. Esto permite que los usuarios de su organización se beneficien de las características de Lync Server incluso cuando trabajan fuera de los firewalls de la organización. También puede federar a sus organizaciones de socios o clientes que ejecutan Lync Server. De esta manera, los usuarios y los socios federados pueden enviar y recibir mensajes INSTANTÁNEos fácilmente, invitar a reuniones y ver la presencia de los demás. Además, los usuarios pueden usar un mensaje de correo electrónico para invitar a conferencias concretas que organicen. Para obtener más información, vea [planear el acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **¿Deseas implementar la telefonía IP empresarial?**     *Telefonía IP empresarial* es la solución de voz sobre IP (VoIP) proporcionada por Lync Server. Ofrece una alternativa atractiva a la telefonía tradicional basada en PBX. La telefonía IP empresarial permite a los usuarios realizar llamadas desde sus equipos o teléfonos VoIP haciendo clic en un contacto en Outlook o Lync Server. Pueden realizar llamadas a través de la red IP de equipo a equipo, de equipo a teléfono o de teléfono a equipo. Los usuarios se benefician de tener todas las opciones de comunicación (voz, correo electrónico, mi y Conferencia) disponibles e integradas en sus equipos. Para obtener más información, consulte [planificación de telefonía empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) en la documentación de planeación.

10. **Si implementa la telefonía IP empresarial, también debe supervisar la calidad de audio de estas llamadas.**    Le recomendamos que use la supervisión para garantizar la calidad de audio de las llamadas de voz de la empresa, si implementa la telefonía IP empresarial. Para obtener más información, vea [planear la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **¿Necesita archivar contenido de mensajería instantánea o contenido de la reunión para fines de cumplimiento?**    Si su organización tiene que archivar contenido de mensajería instantánea o contenido de la reunión con fines de cumplimiento, puede implementar el archivado. Para obtener más información, consulte [planear el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **¿Deseas implementar una conversación persistente?**    Si desea permitir que los usuarios tengan conversaciones en tiempo real que puedan persistir a lo largo del tiempo, puede implementar una conversación persistente. Para obtener más información, consulte [planear el servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **¿Tiene implementado Microsoft Exchange?**    Si su organización usa Microsoft Exchange Server para sus servicios de correo electrónico, puede habilitar varias características que mejoren la utilidad de Lync Server y Microsoft Exchange Server. Algunas de estas características, como mensajería unificada de Exchange (UM), permiten a los usuarios recibir avisos de correo de voz y escuchar el correo de voz de Outlook o Outlook Web Access, para tener acceso a sus buzones de Microsoft Exchange mediante un teléfono y recibir faxes en sus buzones de Microsoft Exchange. Además, si tiene implementado Exchange 2013, puede integrar los almacenes de contactos de los usuarios entre los dos sistemas, usar Exchange para almacenar las fotos de los contactos de mayor resolución e integrar el archivado de los mensajes de correo electrónico y los mensajes instantáneos. Para obtener más información, consulte [planificación de la integración de Exchange Server con Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **¿Tiene sucursales en su organización?**    Si su organización tiene sucursales, Lync Server admite varias formas de soporte técnico y garantiza su resiliencia para voz y otras características. En particular, en una sucursal que no tiene un vínculo de WAN resistente a un centro de datos, puede instalar un equipo de sucursal o un servidor de sucursal que sea más activo para mantener la asistencia de voz empresarial en caso de que el vínculo de la red de área extensa (WAN) se desconecte. Para obtener más información, vea [planear la resistencia de voz de un sitio de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

