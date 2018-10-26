---
title: 'Lync Server 2013: Roles de servidor'
TOCTitle: Roles de servidor
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48275618
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Roles de servidor en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-07_

Todos los servidores que ejecutan Lync Server ejecutan uno o varios *roles del servidor* . Un rol del servidor es un conjunto definido de funcionalidades de Lync Server que proporciona dicho servidor. No es necesario que implemente todos los roles del servidor disponibles en su red. Instale solo los que incluyan la funcionalidad que desee.

Si no está familiarizado con los roles del servidor de Lync Server, la Herramienta de planeación le guiará para encontrar la solución más adecuada para los servidores que desee implementar, en función de las características que desee. En esta sección se proporciona un breve resumen de los roles del servidor y de las características generales que ofrecen:

  - Servidor Standard Edition

  - Servidor front-end y servidor back-end

  - Servidor perimetral

  - Servidor de mediación

  - Director

  - Servidor front-end de chat persistente

  - Almacén de chat persistente (servidor back-end de chat persistente)

  - Almacén de cumplimiento de chat persistente (servidor back-end de cumplimiento de chat persistente)

Para la mayoría de roles del servidor, puede implementar *grupos* de varios servidores que ejecuten el mismo rol del servidor con el fin de obtener una mayor escalabilidad y alta disponibilidad. Todos los servidores de un grupo de servidores deben ejecutar uno o varios roles del servidor idénticos. Para la mayoría de los tipos de grupos de Lync Server, será necesario implementar un equilibrador de carga para repartir el tráfico entre los diferentes servidores del grupo. Lync Server admite tanto el equilibrio de carga del Sistema de nombres de dominio (DNS) como los equilibradores de carga de hardware.

## Servidor Standard Edition

El servidor Standard Edition está diseñado para organizaciones pequeñas y para proyectos piloto de organizaciones de gran tamaño. Permite que muchas de las características de Lync Server, incluidas las bases de datos necesarias, se ejecuten en un solo servidor. Esto le permitirá disponer de la funcionalidad de Lync Server a un precio menor, pero no se trata de una verdadera solución de alta disponibilidad.

El servidor Standard Edition le permite usar mensajería instantánea (MI), presencia, conferencias y Telefonía IP empresarial, todo en ejecución en un solo servidor.

Si desea una solución de alta disponibilidad, use Lync Server Enterprise Edition.

## Servidor front-end y servidor back-end

En Lync Server Enterprise Edition, el servidor front-end es el rol del servidor principal y ejecuta muchas funciones de Lync Server básicas. El servidor front-end, junto con los servidores back-end, son los únicos roles del servidor cuya presencia es necesaria en todas las implementaciones de Lync Server Enterprise Edition.

Un *grupo de servidores front-end* es un conjunto de servidores front-end configurados de forma idéntica que trabajan juntos para proporcionar servicios a un grupo común de usuarios. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.

El servidor front-end incluye:

  - Registro y autenticación de usuarios

  - Información de presencia e intercambio de tarjetas de contacto

  - Servicios de libreta de direcciones y ampliación de la lista de distribución

  - Funcionalidad de MI, incluidas las conferencias de MI de varios participantes

  - Conferencia web, conferencia de acceso telefónico local por y conferencia A/V (si se ha implementado)

  - Servicios de hospedaje de aplicaciones para las dos aplicaciones incluidas en Lync Server (por ejemplo, Operador de conferencia y Aplicación de grupo de respuesta) y para aplicaciones de otros fabricantes

  - Opcionalmente, la supervisión, para recopilar información de uso en forma de registros de detalles de las llamadas (CDR) y registros de errores de las llamadas (CER). Esta información proporciona métricas sobre la calidad de los datos multimedia (audio y vídeo) que atraviesan la red para las llamadas de Telefonía IP empresarial y las conferencias A/V.

  - Componentes web para las tareas basadas en web compatibles, como el Programador web y el Iniciador de participación en reuniones.

  - Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para ver más detalles, consulte [Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación referente a la planeación.
    
    En Lync Server 2010 y versiones anteriores, la supervisión y el archivado no estaban combinados en el servidor front-end, sino que eran roles del servidor independientes.

  - Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.

Los grupos de servidores front-end también son el lugar principal de almacenamiento para los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de la misma en los servidores back-end.

Además, un grupo front-end en la implementación también ejecuta el *Servidor de administración central* , que administra e implementa datos de configuración básicos para todos los servidores que ejecutan Lync Server. El Servidor de administración central también proporciona el Shell de administración de Lync Server y capacidades de transferencia de archivos.

Los servidores back-end son servidores de base de datos que ejecutan Microsoft SQL Server y que proporcionan los servicios de base de datos al grupo de servidores front-end. Los servidores back-end actúan como almacenes de copias de seguridad de los datos de conferencia y de usuario del grupo, y constituyen los lugares principales de almacenamiento para otras bases de datos, como la de grupo de respuesta. Se puede tener un solo servidor back-end, pero se recomienda disponer de una solución que utilice la creación de reflejo de SQL Server para la conmutación por error. Los servidores back-end no ejecutan ningún software de Lync Server.

> [!IMPORTANT]  
> No recomendamos combinar bases de datos de Lync Server con otras bases de datos, ya que puede que la disponibilidad y el rendimiento se vean afectados.



La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.

## Servidor perimetral

El servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios externos a los firewall de la organización. Entre estos usuarios externos se incluyen los usuarios de la organización que están trabajando fuera de la oficina, los usuarios de organizaciones asociadas federadas y los usuarios externos a los que se ha invitado a participar en las conferencias hospedadas en su implementación de Lync Server. El servidor perimetral también permite la conectividad a servicios de conectividad de mensajería instantánea públicos, incluidos Windows Live, AOL, Yahoo\! y Google Talk.

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>


La implementación del servidor perimetral también habilita los servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden utilizar dispositivos móviles compatibles Apple iOS, Android, Windows Phone o Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Asimismo, los dispositivos móviles admiten algunas características de Telefonía IP empresarial, como la unión a conferencias con un clic, la opción Vía trabajo, la conexión con un solo número, el correo de voz y las llamadas perdidas. La característica de movilidad también admite las *notificaciones de inserción* en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.

Los servidores perimetrales también incluyen un proxy totalmente integrado del Protocolo extensible de mensajería y presencia (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para permitir que sus usuarios de Lync Server 2013 agreguen contactos desde socios basados en XMPP (como Google Talk) para la mensajería instantánea y la presencia.

Para obtener más información, consulte [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación sobre planeamiento.

## Servidor de mediación

El servidor de mediación es un componente necesario para la implementación de Telefonía IP empresarial y la conferencia de acceso telefónico local. El servidor de mediación convierte la señalización y, en algunas configuraciones, los medios entre la infraestructura interna de Lync Server y la puerta de enlace de una red telefónica conmutada (RTC) pública, un sistema IP-PBX o un enlace troncal de Protocolo de inicio de sesión (SIP). El servidor de mediación se puede ejecutar combinado en el mismo servidor que el servidor front-end o solo en un grupo del servidor de mediación independiente.

Para obtener más información, consulte [Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md) en la documentación sobre planeamiento.

## Director

Los directores pueden autenticar solicitudes de usuario de Lync Server, pero no hospedan cuentas de usuario ni proporcionan servicios de presencia o conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones que habilitan el acceso de usuarios externos. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no alcanza los servidores front-end. Para más información, vea [Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación sobre planificación.

## Roles del Servidor de chat persistente

El chat persistente permite a los usuarios participar en conversaciones con varios participantes sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente. El servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.

Los servidores que ejecutan Lync ServerStandard Edition también pueden ejecutar el chat persistente combinado en el mismo servidor. No se puede combinar el servidor front-end de chat persistente con el Servidor front-end de Enterprise Edition.

Para ver información detallada, consulte [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

## Vea también

#### Conceptos

[Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md)  

#### Otros recursos

[Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)

