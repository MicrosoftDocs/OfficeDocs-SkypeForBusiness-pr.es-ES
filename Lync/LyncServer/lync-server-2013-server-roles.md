---
title: Lync Server 2013 roles de servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a413bde093c375a887f1ea39c435401b3ce1c4a6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510267"
---
# <a name="server-roles-in-lync-server-2013"></a>Roles de servidor en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Cada servidor que ejecuta Lync Server ejecuta uno o más *roles de servidor*. Un rol de servidor es un conjunto definido de funcionalidades de Lync Server que proporciona el servidor. No es necesario que implemente todos los roles del servidor disponibles en su red. Instale solo los que incluyan la funcionalidad que desee.

Incluso si no está familiarizado con los roles de servidor de Lync Server, la herramienta de planeación puede guiarle a la mejor solución para los servidores que necesita implementar, en función de las características que desee. En esta sección se proporciona un breve resumen de los roles del servidor y de las características generales que ofrecen:

  - Servidor Standard Edition

  - Servidor front-end y servidor back-end

  - Servidor perimetral

  - Servidor de mediación

  - Director

  - Servidor front-end de chat persistente

  - Almacén de chat persistente (servidor back-end de chat persistente)

  - Almacén de cumplimiento de chat persistente (servidor back-end de cumplimiento de chat persistente)

Para la mayoría de roles del servidor, puede implementar *grupos* de varios servidores que ejecuten el mismo rol del servidor con el fin de obtener una mayor escalabilidad y alta disponibilidad. Todos los servidores de un grupo de servidores deben ejecutar uno o varios roles del servidor idénticos. Para la mayoría de los tipos de grupos de servidores de Lync Server, debe implementar un equilibrador de carga para distribuir el tráfico entre los distintos servidores del grupo. Lync Server admite tanto el equilibrio de carga del sistema de nombres de dominio (DNS) como los equilibradores de carga de hardware.

<div>

## <a name="standard-edition-server"></a>Standard Edition Server

El servidor Standard Edition está diseñado para organizaciones pequeñas y para proyectos piloto de organizaciones de gran tamaño. Permite que muchas de las características de Lync Server, incluidas las bases de datos necesarias, se ejecuten en un único servidor. Esto le permite disponer de funcionalidad de Lync Server para un menor costo, pero no proporciona una solución de alta disponibilidad real.

El servidor Standard Edition permite usar la mensajería instantánea (mi), la presencia, la Conferencia y la telefonía IP empresarial, todo ello en un servidor.

Para una solución de alta disponibilidad, use Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Servidor front-end y servidor back-end

En Lync Server Enterprise Edition, el servidor front-end es el rol de servidor principal y ejecuta muchas funciones básicas de Lync Server. El servidor front-end, junto con los servidores back-end, son los únicos roles de servidor necesarios para estar en cualquier implementación de Lync Server Enterprise Edition.

Un *grupo de servidores front-end* es un conjunto de servidores front-end configurados de forma idéntica que trabajan juntos para proporcionar servicios a un grupo común de usuarios. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.

El servidor front-end incluye:

  - Registro y autenticación de usuarios

  - Información de presencia e intercambio de tarjetas de contacto

  - Servicios de libreta de direcciones y ampliación de la lista de distribución

  - Funcionalidad de MI, incluidas las conferencias de MI de varios participantes

  - Conferencia web, conferencia de acceso telefónico local por y conferencia A/V (si se ha implementado)

  - Hospedaje de aplicaciones, para ambas aplicaciones incluidas en Lync Server (por ejemplo, operador de conferencia y aplicación de grupo de respuesta) y aplicaciones de terceros

  - Opcionalmente, la supervisión, para recopilar información de uso en forma de registros de detalles de las llamadas (CDR) y registros de errores de las llamadas (CER). Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) que atraviesan la red tanto para llamadas de telefonía IP empresariales como para conferencias de A/V.

  - Componentes web para las tareas basadas en web compatibles, como el Programador web y Join Launcher.

  - Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.
    
    En Lync Server 2010 y versiones anteriores, la supervisión y el archivado eran roles de servidor independientes, no combinados en el servidor front-end.

  - Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.

Los grupos de servidores front-end también son el lugar principal de almacenamiento para los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de la misma en los servidores back-end.

Además, un grupo de servidores front-end de la implementación también ejecuta el *servidor de administración central*, que administra e implementa datos de configuración básica en todos los servidores que ejecutan Lync Server. El servidor de administración central también proporciona funcionalidad de transferencia de archivos y Shell de administración de Lync Server.

Los servidores back-end son servidores de base de datos que ejecutan Microsoft SQL Server y que proporcionan los servicios de bases de datos para el grupo de servidores front-end. Los servidores back-end actúan como almacenes de copias de seguridad de los datos de conferencia y de usuario del grupo, y constituyen los lugares principales de almacenamiento para otras bases de datos, como la de grupo de respuesta. Puede tener un solo servidor back-end, pero se recomienda una solución que use la creación de reflejos de SQL Server para la conmutación por error. Los servidores back-end no ejecutan ningún software de Lync Server.

<div>


> [!IMPORTANT]  
> No se recomiendan las bases de datos de combinar Lync Server con otras bases de datos. Si lo hace, puede que se vea afectada la disponibilidad y el rendimiento.



</div>

La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.

</div>

<div>

## <a name="edge-server"></a>Servidor perimetral

Servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios fuera de los firewalls de la organización. Estos usuarios externos pueden incluir los propios usuarios de la organización que actualmente trabajan fuera del sitio, usuarios de organizaciones de socios federados y usuarios externos que han invitado a unirse a conferencias hospedadas en su implementación de Lync Server. El servidor perimetral también habilita la conectividad con los servicios de conectividad de mensajería instantánea pública, incluidos Windows Live, AOL, Yahoo \! y Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>



</div>

La implementación del servidor perimetral también habilita los servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden utilizar dispositivos móviles compatibles Apple iOS, Android, Windows Phone o Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas. La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.

Los servidores perimetrales también incluyen un proxy totalmente integrado del Protocolo extensible de mensajería y presencia (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para permitir que los usuarios de Lync Server 2013 puedan agregar contactos de socios basados en XMPP (como Google Talk) para la mensajería instantánea y la presencia.

Para obtener más información, consulte [Planning for external User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación.

</div>

<div>

## <a name="mediation-server"></a>Servidor de mediación

El servidor de mediación es un componente necesario para implementar la telefonía IP empresarial y la Conferencia de acceso telefónico local. El servidor de mediación traduce la señalización y, en algunas configuraciones, los medios entre la infraestructura interna de Lync Server y una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un tronco de protocolo de inicio de sesión (SIP). El servidor de mediación se puede ejecutar combinado en el mismo servidor que el servidor front-end o solo en un grupo del servidor de mediación independiente.

Para obtener más información, consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="director"></a>Director

Los directores pueden autenticar solicitudes de usuario de Lync Server, pero no alojan cuentas de usuario ni proporcionan servicios de presencia o conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones que habilitan el acceso de usuarios externos. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no alcanza los servidores front-end. Para obtener más información, consulte [escenarios del Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Roles de servidor de chat persistente

El chat persistente permite a los usuarios participar en conversaciones con varios participantes sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente. El servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.

Los servidores que ejecutan Lync Server Standard Edition también pueden ejecutar chat persistente colocado en el mismo servidor. No puede combinar el servidor front-end de chat persistente con el servidor front-end Enterprise Edition.

Para obtener más información, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Consulte también


[Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Escenarios para el Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

