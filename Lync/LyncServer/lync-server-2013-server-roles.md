---
title: 'Lync Server 2013: Roles de servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8c5b052defcdc1d60ef9900c283f9f50b3809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Roles de servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Cada servidor que ejecuta Lync Server ejecuta uno o varios *roles de servidor*. Un rol de servidor es un conjunto definido de funcionalidades de Lync Server proporcionadas por ese servidor. No es necesario implementar todos los roles de servidor disponibles en la red. Instale solo los que incluyan la funcionalidad que desee.

Incluso si no está familiarizado con los roles de servidor de Lync Server, la herramienta de planeación puede guiar la mejor solución para los servidores que necesita implementar, en función de las características que desee. Esta sección proporciona una breve introducción a los roles de servidor y las características generales que proporcionan:

  - Servidor Standard Edition

  - Servidor front-end y servidor back-end

  - Servidor perimetral

  - Servidor de mediación

  - Director

  - Servidor front-end de chat persistente

  - Almacén de chat persistente (servidor de back-end de chat persistente)

  - Almacén de cumplimiento de chat persistente (servidor back end de cumplimiento de chat persistente)

Para la mayoría de roles del servidor, puede implementar *grupos* de varios servidores que ejecuten el mismo rol del servidor para, así, obtener una mayor escalabilidad y alta disponibilidad. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Para la mayoría de los tipos de grupos de servidores de Lync, debe implementar un equilibrador de carga para distribuir el tráfico entre los distintos servidores del grupo. Lync Server admite el equilibrio de carga del sistema de nombres de dominio (DNS) y los equilibradores de carga de hardware.

<div>

## <a name="standard-edition-server"></a>Servidor Standard Edition

El servidor Standard Edition está diseñado para pequeñas organizaciones y para proyectos piloto de organizaciones grandes. Permite que muchas de las características de Lync Server, incluidas las bases de datos necesarias, se ejecuten en un solo servidor. Esto le permite tener la funcionalidad de Lync Server a un costo menor, pero no proporciona una verdadera solución de alta disponibilidad.

El servidor Standard Edition le permite usar la mensajería instantánea (mi), presencia, Conferencia y telefonía IP empresarial, todo en un mismo servidor.

Para obtener una solución de alta disponibilidad, use Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Servidor front-end y servidor back-end

En Lync Server Enterprise Edition, el servidor front-end es el rol de servidor principal y ejecuta muchas funciones básicas de Lync Server. El servidor front-end, junto con los servidores back-end, son los únicos roles de servidor que deben estar en cualquier implementación de Lync Server Enterprise Edition.

Un *Grupo front-end* es un conjunto de servidores front-end, configurado de manera idéntica, que funcionan conjuntamente para proporcionar servicios a un grupo común de usuarios. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.

El servidor front-end incluye lo siguiente:

  - Autenticación y registro de usuarios

  - Información de presencia y de la tarjeta de contacto

  - Servicios de libreta de direcciones y expansión de la lista de distribución

  - Funciones de mensajería instantánea, incluidas las conferencias de mensajería instantánea entre varias partes

  - Conferencia Web, Conferencia de acceso telefónico local RTC y conferencia A/V (si se ha implementado)

  - Hospedaje de aplicaciones, para las dos aplicaciones incluidas con Lync Server (por ejemplo, el operador de conferencias y la aplicación de grupo de respuesta) y aplicaciones de terceros

  - Opcionalmente, la supervisión, para recopilar información de uso en forma de registros detallados de llamadas (CDR) y registros de errores de llamadas (CER). Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) que atraviesan tu red tanto las llamadas de voz empresariales como las conferencias A/V.

  - Componentes web para las tareas basadas en web compatibles, como el Programador web y el Iniciador de participación en reuniones.

  - Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para obtener más información, vea [planificación de archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.
    
    En Lync Server 2010 y versiones anteriores, la supervisión y el archivado eran roles de servidor diferentes, no colocados en el servidor front-end.

  - Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.

Los grupos de servidores front-end también son el lugar principal de almacenamiento de los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de esta información en los servidores back-end.

Además, un grupo de servidores front-end de la implementación también ejecuta el *servidor de administración central*, que administra e implementa los datos de configuración básica de todos los servidores que ejecutan Lync Server. El servidor de administración central también proporciona capacidades de Shell de administración y transferencia de archivos de Lync Server.

Los servidores back-end son servidores de base de datos que ejecutan Microsoft SQL Server y que proporcionan los servicios de base de datos para el grupo de servidores front-end. Los servidores back-end actúan como almacenes de copias de seguridad de los datos de conferencia y de usuario del grupo y, asimismo, constituyen los lugares principales de almacenamiento para otras bases de datos, como la de grupo de respuesta. Puede tener un único servidor de servicios de fondo, pero se recomienda usar el reflejo de SQL Server para la conmutación por error. Los servidores back-end no ejecutan software de Lync Server.

<div>


> [!IMPORTANT]  
> No recomendamos collocating bases de datos de Lync Server con otras bases de datos. Si lo hace, la disponibilidad y el rendimiento pueden verse afectados.



</div>

La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.

</div>

<div>

## <a name="edge-server"></a>Servidor perimetral

El servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios ajenos a los firewalls de la organización. Estos usuarios externos pueden incluir los usuarios de la organización que actualmente están trabajando fuera del sitio, los usuarios de organizaciones de socios federados y los usuarios externos que han recibido una invitación para unirse a conferencias hospedadas en su implementación de Lync Server. El servidor perimetral también permite la conectividad con servicios de conectividad de mensajería instantánea pública, como Windows\!Live, AOL, Yahoo y Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>



</div>

La implementación de servidor perimetral también permite servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden usar dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y llamadas perdidas. La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.

Los servidores perimetrales también incluyen un proxy totalmente integrado de Extensible Messaging and Presence Protocol (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para permitir a los usuarios de Lync Server 2013 agregar contactos de socios basados en XMPP (como Google Talk) para la mensajería instantánea y la presencia.

Para obtener más información, vea [planificación para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.

</div>

<div>

## <a name="mediation-server"></a>Servidor de mediación

Servidor de mediación es un componente necesario para implementar la telefonía IP empresarial y las conferencias de acceso telefónico local. Servidor de mediación traduce la señalización y, en algunas configuraciones, medios entre la infraestructura interna de Lync Server y una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un tronco de protocolo de inicio de sesión (SIP). Puede ejecutar el servidor de mediación en el mismo servidor que el servidor front-end o separarlo en un grupo de servidores de mediación independiente.

Para obtener más información, vea [componente de servidor de mediación en Lync server 2013](lync-server-2013-mediation-server-component.md) en la documentación de planeación.

</div>

<div>

## <a name="director"></a>Director

Los directores pueden autenticar solicitudes de usuario de Lync Server, pero no alojan cuentas de usuario ni proporcionan servicios de presencia o de conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones donde el acceso de usuarios externos está permitido. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no llega los servidores front-end. Para obtener más información, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación de planeación.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Roles de servidor de chat persistentes

El chat persistente permite a los usuarios participar en conversaciones entre varias entidades sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente, mientras que el servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.

Los servidores que ejecutan Lync Server Standard Edition también pueden ejecutar una conversación persistente colocada en el mismo servidor. No puede Collocate el servidor front-end de chat persistente con el servidor front-end Enterprise Edition.

Para obtener más información, consulte [planear el servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Componente de servidor de mediación de Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

