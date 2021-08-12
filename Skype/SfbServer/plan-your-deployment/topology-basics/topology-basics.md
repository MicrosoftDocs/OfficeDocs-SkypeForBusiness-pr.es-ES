---
title: Conceptos básicos de topología para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumen: elija la topología para Skype Empresarial Server. Obtenga información sobre la ubicación del servidor para Skype Empresarial Server.'
ms.openlocfilehash: 922bc26ee6eeea720c62cbbc744953aa5edecf4c03a792fac56ee7910806b6e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349872"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Conceptos básicos de topología para Skype Empresarial Server

**Resumen:** Elija la topología para Skype Empresarial Server. Obtenga información sobre la ubicación del servidor para Skype Empresarial Server.

Antes de preparar cualquier otra cosa, querrá saber que está planeando la topología adecuada para la implementación de Skype Empresarial Server. Lo primero que debe decidir es si va a tener una implementación local de Skype Empresarial Server o si va a combinar esto con una implementación de Skype Empresarial Server Online en una implementación híbrida. En cualquier caso, querrá leer más lejos, ya que detallaremos las topologías locales aquí, pero los detalles híbridos se documentan en su propia sección.

También puede ver algunas topologías de ejemplo en [Topologías de referencia para Skype Empresarial Server](reference-topologies.md).

## <a name="sites"></a>Sitios

En Skype Empresarial Server, se definen sitios de la red que contienen Skype Empresarial Server componentes. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que Skype Empresarial Server sitios son un concepto independiente de los sitios de Servicios de dominio de Active Directory y Microsoft Exchange Server web. Los Skype Empresarial Server no necesitan corresponder a los sitios de Active Directory.

Skype Empresarial Server la implementación local de uno o varios sitios que se pueden escalar según los requisitos de alta disponibilidad y ubicación.

La implementación tendrá al menos un sitio central (también denominado centro de datos, este es un centro de datos para todos los servidores ubicados en él) y cada sitio central de la implementación tendrá un servidor Standard Edition o al menos un grupo de servidores front-end Enterprise Edition. Puede ver las diferencias en cada opción a continuación:

- Standard Edition servidor incluye una base de datos SQL Server Express de datos.

- Enterprise Edition El grupo de servidores front-end incluye:

  - Uno o más servidores front-end (idealmente al menos tres, para escalabilidad), con un máximo de doce. El equilibrio de carga sería necesario para más de un servidor.

  - Un servidor back-end independiente.

Puede obtener más información sobre los distintos roles de servidor un poco más adelante en esta sección.

Además de los sitios centrales, también puede terminar teniendo uno o varios sitios de sucursal asociados con el sitio central. Dependen del sitio central para casi todas sus funciones, ¿de qué están hechos exactamente?

- Aplicación de sucursal con funciones de supervivencia, que combina una puerta de enlace de red telefónica conmutada (RTC), con algunas funciones Skype Empresarial Server servicio.

- Servidor de sucursal con funciones de supervivencia, es un servidor que ejecuta Windows que tiene instalado Skype Empresarial Server registrador y servidor de mediación.

- Puerta de enlace RTC independiente (que no forma parte de la aplicación de sucursal con funciones de supervivencia).

- Servidor de mediación independiente o grupo de servidores de mediación independiente (si no desea asociar este rol con la aplicación de sucursal con funciones de supervivencia).

## <a name="whats-in-a-skype-for-business-server-site"></a>¿Qué hay en un Skype Empresarial Server web?

Para obtener más información, un sitio central también puede tener:

- Varios grupos de servidores front-end, en el mismo dominio o dominios diferentes (recuerde que todos los servidores front-end de un grupo de servidores front-end, junto con los servidores back-end del grupo de servidores, deben estar en el mismo dominio).

- Varios servidores Standard Edition.

- Office Web Apps Server, que se usa con Office web apps en Skype Empresarial Server para compartir y representar PowerPoint presentaciones.

- Servidor perimetral o grupo de servidores perimetrales (en una red perimetral). Es necesario si desea que la implementación admita socios federados, conectividad de mensajería instantánea pública, puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) y acceso remoto de usuarios. Puede encontrar más detalles en la documentación de planeación del servidor perimetral.

- Servidor de chat persistente. Es útil si desea que los usuarios puedan participar en conversaciones multipartes basadas en temas que persisten con el tiempo. Hay más información en el tema Planning for Persistent Chat Server.

- Supervisión. Se usa para admitir la recopilación de datos para audio/vídeo (A/V) Calidad de la experiencia (QoE) y grabación de detalles de llamadas (CDR) para conferencias de Telefonía IP empresarial y A/V en la implementación. Se trata detalladamente en el tema Planning for Monitoring.

- Director o grupo de directores. No es necesario, pero es útil si desea mejorar la resistencia y habilitar la redirección de Skype Empresarial solicitudes de usuario al grupo de servidores principal del usuario. Si desea implementar directores, se admite un máximo de 10 por grupo. Si esto es algo que necesita, definitivamente continúe leyendo en el tema Planning for Directors.

- Proxy inverso No se trata de un componente de Skype Empresarial Server, pero si desea admitir el uso compartido de contenido web para usuarios federados, si quiere admitir el tráfico de movilidad, si los usuarios remotos desean usar la libreta de direcciones, unirse a reuniones, entre otras cosas, esto es algo que querrá tener en su entorno. Hay un tema Configuración del servidor proxy inverso que puede consultar para obtener más información, cuando esté listo.

A continuación encontrará información adicional sobre la ubicación de estos servidores.

Todos los grupos de servidores front-end Standard Edition servidores implementados en el sitio central comparten lo siguiente, suponiendo que los haya implementado:

||||
|:-----|:-----|:-----|
|Director o grupo de directores  <br/> |Servidor de mediación independiente o grupo de servidores de mediación  <br/> |Servidor Office Web Apps  <br/> |
|Servidor perimetral o grupo perimetral  <br/> |Servidor de chat persistente o grupo de servidores de chat persistente  <br/> |Supervisión  <br/> |

¿Dónde Exchange de mensajería unificada (UM) en esta lista? Bueno, ciertamente puede usarlo con Skype Empresarial Server si desea integrarse con la mensajería unificada de Exchange, pero no es un componente del sitio de Skype Empresarial Server, por lo que no lo mencionamos aquí.

Puede que esté planeando tener varios sitios centrales y, si es así, pueden compartir los siguientes servidores y roles, si están implementados en el sitio central:

|||
|:-----|:-----|
|Servidor de mediación independiente o grupo de servidores de mediación  <br/> |Servidor perimetral o grupo perimetral  <br/> |
|Servidor de chat persistente o grupo de servidores de chat persistente  <br/> |Supervisión  <br/> |

Al igual que la última lista, no estamos incluyendo el servidor de mensajería unificada de Exchange aquí porque no forma parte de la implementación de Skype Empresarial Server, sino que también se encuentra en la misma categoría aquí.

Hay otros componentes y opciones que van a las implementaciones, por supuesto.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |Puertas de enlace RTC (si implementa Telefonía IP empresarial  <br/> |Exchange Servidor de mensajería unificada (si desea integrar con Exchange um)  <br/> |Equilibrio de carga de DNS  <br/> |
|Equilibradores de carga de hardware  <br/> |Bases de datos SQL Server  <br/> |Recursos compartidos de archivos  <br/> ||

## <a name="server-roles"></a>Funciones de servidor

Cada servidor que Skype Empresarial Server ejecuta uno o más roles de servidor. Un rol de servidor es un conjunto definido de Skype Empresarial Server funcionalidades proporcionadas por ese servidor. No es necesario implementar todos los roles de servidor disponibles en la red. Instale solo los que incluyan la funcionalidad que desee.

Para la mayoría de roles del servidor, puede implementar grupos de varios servidores que ejecuten el mismo rol del servidor con el fin de obtener una mayor escalabilidad y alta disponibilidad. Cada servidor en un grupo debe ejecutar un rol o roles de servidores idénticos. Para la mayoría de los tipos de grupos Skype Empresarial Server, debe implementar un equilibrador de carga para propagar el tráfico entre los distintos servidores del grupo. Skype Empresarial Server es compatible con equilibrio de carga del Sistema de nombres de dominio (DNS) y equilibradores de carga de hardware.

### <a name="front-end-server-and-back-end-server"></a>Servidor front-end y servidor back-end

En Skype Empresarial Server Enterprise Edition, el servidor front-end es el rol de servidor principal y ejecuta muchas funciones Skype Empresarial Server servidor. El servidor front-end, junto con los servidores back-end, son los únicos roles de servidor necesarios para estar en cualquier Skype Empresarial Server Enterprise Edition implementación.

Un grupo de servidores front-end es un conjunto de servidores front-end configurados de forma idéntica que trabajan juntos para proporcionar servicios a un grupo común de usuarios. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.

El servidor front-end incluye:

- Autenticación y registro de usuarios.

- Información de presencia e intercambio de tarjetas de contacto.

- Servicios de libreta de direcciones y expansión de listas de distribución.

- Funcionalidad de mensajería instantánea, incluidas las conferencias de mensajería instantánea multiparte.

- Conferencia web, conferencia de acceso telefónico local RTC y conferencia A/V (si se implementa).

- Hospedaje de aplicaciones, para ambas aplicaciones incluidas con Skype Empresarial Server (por ejemplo, Operador de conferencia y aplicación de grupo de respuesta) y aplicaciones de terceros.

- Opcionalmente, la supervisión, para recopilar información de uso en forma de registros de detalles de las llamadas (CDR) y registros de errores de las llamadas (CER). Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) que atraviesan la red tanto para llamadas Telefonía IP empresarial como para conferencias A/V.

- Componentes web para las tareas basadas en web compatibles, como el Programador web y Join Launcher.

- Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para ver más detalles, consulte [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) en la documentación referente a la planeación.

    En Lync Server 2010 y versiones anteriores, la supervisión y el archivado eran roles de servidor independientes, no se colocaban en el servidor front-end.

- Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.

Los grupos de servidores front-end también son el lugar principal de almacenamiento para los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de la misma en los servidores back-end.

Además, un servidor front-end de la implementación también ejecuta el servidor de administración central, que administra e implementa datos de configuración básicos en todos los servidores que ejecutan Skype Empresarial Server. El servidor de administración central también proporciona funcionalidades de Shell de administración de Lync Server y transferencia de archivos.

Los servidores back-end son servidores de base de datos que Microsoft SQL Server que proporcionan los servicios de base de datos para el grupo de servidores front-end. Los servidores back-end sirven como almacenes de copia de seguridad para los datos de usuario y conferencia del grupo y son los almacenes principales de otras bases de datos, como la base de datos del grupo de respuesta. Puede tener un único servidor back-end, pero se recomienda la alta disponibilidad del servidor [back-end Skype Empresarial Server](../high-availability-and-disaster-recovery/back-end-server.md) para la conmutación por error. Los servidores back-end no ejecutan ningún Skype Empresarial Server software.

> [!IMPORTANT]
> No se recomienda la Skype Empresarial Server bases de datos con otras bases de datos. Si lo hace, la disponibilidad y el rendimiento pueden verse afectados.

> [!NOTE]
> SQL La creación de reflejos está disponible Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error se prefieren Skype Empresarial Server 2019.

La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.

### <a name="edge-server"></a>Servidor perimetral

El servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios fuera de los firewalls de la organización. Estos usuarios externos pueden incluir los propios usuarios de la organización que están trabajando actualmente fuera del sitio, los usuarios de organizaciones asociadas federadas y los usuarios externos que han sido invitados a unirse a conferencias hospedadas en su implementación Skype Empresarial Server web.

La implementación del servidor perimetral también habilita los servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden utilizar dispositivos móviles compatibles Apple iOS, Android, Windows Phone o Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Asimismo, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas. La característica de movilidad también admite las notificaciones de inserción en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.

Los servidores perimetrales también incluyen un proxy totalmente integrado del Protocolo extensible de mensajería y presencia (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para permitir a los usuarios de Skype Empresarial Server agregar contactos de socios basados en XMPP para la mensajería instantánea y la presencia.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.

### <a name="mediation-server"></a>Servidor de mediación

El servidor de mediación es un componente necesario para implementar Telefonía IP empresarial, llamar a través del trabajo y conferencias de acceso telefónico local. El servidor de mediación traduce la señalización y, en algunas configuraciones, los medios entre la infraestructura interna de Skype Empresarial Server y una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un tronco del Protocolo de inicio de sesión (SIP). El servidor de mediación se puede ejecutar combinado en el mismo servidor que el servidor front-end o solo en un grupo del servidor de mediación independiente.

Para obtener más información, vea [Mediation Server component in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Servidor de interoperabilidad de vídeo

El servidor de interoperabilidad de vídeo es un nuevo rol a partir Skype Empresarial Server 2015. Le permite integrar su implementación Skype Empresarial Server con determinadas soluciones VTC (sistema de teleconferencia de vídeo) de terceros. Un VIS actúa como intermediario entre un sistema de teleconferencia de terceros y una implementación Skype Empresarial Server terceros. Para esta versión, VIS se centra en la interoperabilidad con sistemas de vídeo de Cisco/Tandberg.

Para obtener más información, vea [Plan for Video Interop Server in Skype Empresarial Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Los directores pueden Skype Empresarial Server solicitudes de usuario, pero no las cuentas de usuario principales ni proporcionan servicios de presencia o conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones que habilitan el acceso de usuarios externos. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no alcanza los servidores front-end.

### <a name="persistent-chat-server-roles"></a>Roles de servidor de chat persistente

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015.

El chat persistente permite a los usuarios participar en conversaciones con varios participantes sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente. El servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.

Los servidores que Skype Empresarial Server Standard Edition también pueden ejecutar chat persistente en el mismo servidor. No puede asociar el servidor front-end de chat persistente Enterprise Edition servidor front-end.

Para obtener más información, vea [Plan for Persistent Chat Server in Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Compatibilidad con alta disponibilidad y recuperación ante desastres

Skype Empresarial Server proporciona alta disponibilidad por redundancia de servidor mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.

Skype Empresarial Server también proporciona medidas de recuperación ante desastres al habilitar el emparejamiento de grupo. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.

Skype Empresarial Server también admite varias opciones para la alta disponibilidad del servidor back-end. Entre ellas se incluyen las siguientes:

- Creación de reflejos de base de datos

- Grupos de disponibilidad AlwaysOn

- Instancias del clúster de conmutación por error AlwaysOn (FCI)

- SQL clústeres de conmutación por error

Para obtener más información sobre el emparejamiento de grupos y la alta disponibilidad del servidor [back-end,](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)vea Plan for high availability and disaster recovery in Skype Empresarial Server .

## <a name="server-collocation-in-skype-for-business-server"></a>Ubicación del servidor en Skype Empresarial Server

Ya hemos usado el término colocate, pero ¿qué significa esto? Skype Empresarial Server permite localizar algunos roles y características de servidor en el mismo servidor, que es la colocación, o en servidores diferentes, pero puede resultar confuso al empezar y si está realizando una implementación de servidor Standard Edition o Enterprise Edition (cada uno de ellos viene con sus propias reglas). Para ayudarle con la planeación, estamos incluyendo la colocación de servidores en implementaciones de servidor de Standard Edition e implementaciones de grupo de servidores front-end de Enterprise Edition (en la mayoría de los casos, esta información es idéntica y, cuando es diferente, se llama específicamente).

### <a name="collocation-of-server-roles"></a>Colocación de roles de servidor

El servidor Standard Edition tiene el siguiente rol instalado (sin embargo, se requiere una configuración adicional), mientras que en el grupo de servidores front-end de Enterprise Edition, este rol se puede colocar o implementar en un servidor independiente:

- Mediación

Estos roles de servidor deben implementarse en un servidor independiente:

- Director

- Microsoft Edge

- Servidor de interoperabilidad de vídeo

- Office Web Apps

### <a name="databases"></a>Databases

Este es el área con diferencias reales entre las implementaciones de servidores de Standard Edition y las implementaciones de grupo de servidores Enterprise Edition, por lo que tendremos dos secciones a continuación, seguidas de algunas reglas adicionales para ambas.

#### <a name="standard"></a>Estándar

Dado SQL Server Express se coloca en el servidor Standard Edition y no se puede mover, esto es bastante sencillo. Además, si implementa el servidor de chat persistente en un servidor de Standard Edition, también podrá colocar el chat persistente y la base de datos de cumplimiento de chat persistente en el servidor de Standard Edition, pero no es así.

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015.

No se pueden colocar en el servidor Standard Edition, pero pueden ir en un único servidor de base de datos propio:

- Base de datos de supervisión

- Base de datos de archivado

- Cualquier base de datos back-end para un grupo Enterprise Edition front-end

#### <a name="enterprise"></a>Enterprise

Las siguientes bases de datos se pueden colocar en el mismo servidor back-end SQL Server:

- Base de datos back-end

- Base de datos de supervisión

- Base de datos de archivado

- Base de datos de chat persistente

- Base de datos de cumplimiento de chat persistente

#### <a name="both"></a>Ambas

Ahora, hay que seguir algunas reglas adicionales al colocar bases de datos Skype Empresarial Server en una única instancia de SQL o en varias instancias SQL en la misma base de datos SQL Server datos:

- Cada instancia SQL solo puede contener una sola base de datos back-end para un grupo de servidores front-end de Enterprise Edition, una única base de datos de supervisión, una única base de datos de archivado, una única base de datos de chat persistente y una única base de datos de cumplimiento de chat persistente.

- El servidor de bases de datos no puede admitir más de un grupo de servidores front-end de Enterprise Edition, un servidor que ejecuta archivado, un servidor que ejecuta supervisión, una única base de datos de chat persistente y una única base de datos de cumplimiento de chat persistente, pero puede admitir uno de cada uno, independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.

    > [!NOTE]
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015.

### <a name="file-shares"></a>Recursos compartidos de archivos

El recurso compartido de archivos puede estar en un servidor independiente o puede colocarlo en el mismo servidor que cualquiera o todos los siguientes:

- Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition

- Base de datos de supervisión

- Base de datos de archivado

- Base de datos de chat persistente

- Base de datos de cumplimiento de chat persistente

> [!CAUTION]
> Tenga en cuenta que, aunque puede colocar el recurso compartido de archivos en estos servidores, es fundamental tener en cuenta que no se recomienda. Si va a asociar el recurso compartido de archivos con cualquier otro rol de servidor, asegúrese de que está supervisando los problemas de espacio en disco y rendimiento de forma regular.

### <a name="keep-in-mind"></a>Recuerde

- No puede colocar un servidor proxy inverso, que no es un componente Skype Empresarial Server y puede que ni siquiera esté en la topología. Necesitará un proxy inverso si desea admitir el uso compartido de contenido web para usuarios federados, entre muchas otras cosas. Si es necesario, implemente la compatibilidad con proxy inverso para Skype Empresarial Server mediante la configuración de un servidor proxy inverso existente que ya esté en su organización que esté siendo usado por otras aplicaciones.

- No puede asociar ningún componente Exchange um o SharePoint server con ningún rol Skype Empresarial Server usuario.

## <a name="see-also"></a>Consulte también

[Topologías de referencia para Skype Empresarial Server](reference-topologies.md)