---
title: Lync Server 2013 decisiones iniciales de planeación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1fd48d59aedcab3d203b8d15be34cbec84b01a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Decisiones iniciales de planeación para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La primera parte del proceso de planeación consiste en decidir qué cargas de trabajo de Lync Server y qué características principales desea para su organización.

1.  **¿Desea una implementación local o en línea?**    Lync Server admite ambos escenarios de implementación. Para obtener más información sobre cómo tomar esta decisión, consulte [decidir cómo implementar Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md), que aparece anteriormente en esta sección.

2.  **¿Desea una topología física o virtualizada?**    Lync Server admite todas las cargas de trabajo y roles de servidor tanto en topologías físicas como virtualizadas. La capacidad de usuarios y la escalabilidad varían entre las topologías físicas y las virtuales. Para obtener más información, consulte [Running Lync Server 2013 en servidores virtuales](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **La mensajería instantánea *(mi)* y la *presencia* siempre están habilitadas.**    En cualquier implementación de Lync Server, la carga de trabajo de mensajería instantánea y presencia está instalada y habilitada de forma predeterminada. La mensajería instantánea permite a los usuarios comunicarse con mensajes de texto en tiempo real y la presencia les permite ver el estado de otros usuarios en la red. El estado de presencia de un usuario proporciona información para que a los demás les sea más fácil decidir si intentan ponerse en contacto con él y de qué forma. Para obtener más información, consulte [planeación de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) en la documentación referente a la planeación.

4.  **¿Desea implementar cualquier modo de conferencia?**    La Conferencia es otra de las características principales de Lync Server. Se admiten varios modos de conferencia. Puede elegir entre implementar todos los tipos de conferencia admitidos o solo algunos de ellos. La *conferencia web* permite a los usuarios ver un archivo, como un conjunto de diapositivas creado con el programa de gráficos de presentación Microsoft PowerPoint, que se esté presentando. El *uso compartido de aplicaciones* permite a los usuarios compartir todo su escritorio o una parte del mismo con el resto de usuarios en tiempo real. Con la *conferencia A/V*, los usuarios pueden agregar audio (y posiblemente vídeo) a sus conferencias y comunicaciones de punto a punto. La *conferencia de acceso telefónico local* permite a los usuarios usar teléfonos RTC estándar para participar en la parte de audio de conferencias hospedadas en su organización. Para obtener más información, consulte [Planning for Conferencing in Lync Server 2013](lync-server-2013-planning-for-conferencing.md) en la documentación de planeación.
    
    En Lync Server 2013, si implementa la conferencia Web, también debe planear la integración con Office Web Apps Server para habilitar el uso compartido y la visualización de PowerPoint en reuniones. Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Si implementa la conferencia A/V, también debe supervisar la calidad de audio de estas conferencias.**    Hay muchos factores que afectan a la calidad de audio y vídeo de las conferencias A/V de Lync Server. Con la supervisión, puede supervisar la calidad de A/V de las llamadas y las conferencias. Puede detectar problemas que afectan a la calidad de medios y garantizar que los usuarios tengan la mejor experiencia de medios posible. Para obtener más información, consulte [planeación de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **¿Desea obtener alta disponibilidad para sus servidores de mensajería instantánea, presencia y Conferencia?**    Si solo tiene un servidor en un sitio que proporciona características de mensajería instantánea, presencia y Conferencia, la productividad de los usuarios se verá afectada en gran medida si el servidor deja de funcionar. Mediante la implementación de un *Grupo* de servidores Enterprise Edition de al menos tres servidores para estas funciones, es posible que Lync Server continúe funcionando con todas estas características intactas incluso si un servidor no está disponible.
    
    Otra opción para las organizaciones con 5000 o menos usuarios que desean una alta disponibilidad es implementar dos servidores que ejecuten Lync Server Standard Edition y emparejar estos servidores de forma conjunta. Para obtener más información, consulte [planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **¿Desea opciones de recuperación ante desastres?**    Si tiene dos centros de recursos y desea opciones de recuperación ante desastres para permitir que los usuarios sigan funcionando si todos o muchos de los servidores de un centro de trabajo se desplazan, puede implementar los servidores teniendo en cuenta la recuperación ante desastres. En esta implementación, empareje un grupo de servidores de un centro de datos con el grupo correspondiente de otro centro de datos. Si un centro de datos deja de funcionar, el otro grupo del par prestará servicio a los usuarios de los dos grupos de servidores con una interrupción mínima de los servicios. Para obtener más información, consulte [planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **¿Desea permitir que los usuarios se comuniquen y colaboren con los usuarios externos?**    La habilitación de la comunicación y la colaboración con usuarios externos puede aumentar el retorno de la inversión en Lync Server. Esto permite que los propios usuarios de su organización se beneficien de las características de Lync Server, incluso cuando trabajan fuera de los firewalls de la organización. También puede federar a sus organizaciones de asociados o clientes que ejecutan Lync Server. De esta forma, los usuarios y los usuarios socios federados pueden enviar y recibir mensajes instantáneos, invitar a otros usuarios a reuniones y ver la presencia de otros usuarios con facilidad. Además, los usuarios pueden enviar un correo electrónico para invitar a usuarios externos específicos a conferencias que ellos mismos organicen. Para obtener más información, consulte [planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **¿Desea implementar la telefonía IP empresarial?** La     *telefonía IP empresarial* es la solución de voz sobre IP (VoIP) que proporciona Lync Server. Se trata de una atractiva alternativa a la telefonía tradicional basada en PBX. La telefonía IP empresarial permite a los usuarios realizar llamadas desde sus equipos o teléfonos VoIP haciendo clic en un contacto en Outlook o Lync Server. Pueden realizar llamadas a través de la red IP de un PC a otro, de un PC a un teléfono o de un teléfono a un PC. Los usuarios disponen de todas las opciones de comunicación (voz, correo electrónico, mensajería instantánea y conferencia) integradas en su equipo. Para obtener más información, consulte [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) en la documentación referente a la planeación.

10. **Si implementa la telefonía IP empresarial, también debe supervisar la calidad de audio de estas llamadas.**    Le recomendamos que use la supervisión para garantizar la calidad de audio de las llamadas de telefonía IP empresarial, si implementa la telefonía IP empresarial. Para obtener más información, consulte [planeación de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **¿Necesita archivar contenido de mensajería instantánea o contenido de reuniones por motivos de cumplimiento?**    Si su organización tiene que archivar contenido de mensajería instantánea o contenido de reuniones con fines de cumplimiento, puede implementar el archivado. Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **¿Desea implementar chat persistente?**    Si quiere permitir que los usuarios tengan conversaciones en tiempo real que puedan persistir a lo largo del tiempo, puede implementar chat persistente. Para obtener más información, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **¿Tiene implementado Microsoft Exchange?**    Si su organización usa Microsoft Exchange Server para sus servicios de correo electrónico, puede habilitar varias características que mejoran la utilidad de Lync Server y Microsoft Exchange Server. Algunas de estas características, denominadas mensajería unificada de Exchange (UM), incluyen la habilitación de usuarios para recibir avisos de correo de voz y escuchar correo de voz desde Outlook o Outlook Web Access, para obtener acceso a sus buzones de Microsoft Exchange mediante un teléfono y recibir faxes en sus buzones de Microsoft Exchange. Además, si tiene implementado Exchange 2013, puede integrar los almacenes de contactos para los usuarios entre los dos sistemas, usar Exchange para almacenar fotos de contactos con una resolución superior e integrar el archivado de mensajes instantáneos y de correo electrónico. Para obtener más información, consulte [planeación de la integración de Exchange Server con Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **¿Tiene sucursales en su organización?**    Si su organización tiene sucursales, Lync Server admite varias formas de admitirlas y garantizar su resiliencia para voz y otras características. En concreto, en una sucursal que no tiene un vínculo WAN resistente a un centro de datos, puede instalar una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia para mantener la compatibilidad con la telefonía IP empresarial en caso de que el vínculo de la red de área extensa (WAN) se desconecte. Para obtener más información, consulte [Planning for Branch-site Voice Resiliency en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

