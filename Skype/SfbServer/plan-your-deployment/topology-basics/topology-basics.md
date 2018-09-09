---
title: Conceptos básicos de la topología de Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumen: Elija la topología de Skype para Business Server. Obtenga información sobre la combinación de servidor de Skype para Business Server.'
ms.openlocfilehash: 5d2589d6ba7878ea69c8860ad99f182912e471dd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886168"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Conceptos básicos de la topología de Skype para Business Server

**Resumen:** Elija la topología de Skype para Business Server. Obtenga información sobre la combinación de servidor de Skype para Business Server.

Antes de preparar nada más, desea saber que está planeando para la topología correcta para la implementación de Skype para Business Server. Lo primero que hay que decidir es si va a tener una implementación local de Skype para Business Server, o si va a combinar esto con un Skype para la implementación de servidor en línea de negocio en una implementación híbrida. En cualquier caso, va a desea leer más, tal y como se aquí se detallan aquí las topologías local, pero se documentan los detalles híbrida en su propia sección.

También puede ver algunos ejemplos de topologías en [las topologías de referencia de Skype para Business Server](reference-topologies.md).

## <a name="sites"></a>Sitios

En Skype para Business Server, es posible definir sitios en la red que contienen Skype para los componentes de Business Server. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que Skype para sitios de Business Server son un concepto independiente de los sitios de los servicios de dominio de Active Directory y los sitios de Microsoft Exchange Server. No es necesario que su Skype para sitios de Business Server corresponden a los sitios de Active Directory.

Skype para Business Server es compatible con la implementación local de uno o varios sitios que se puede escalar según la alta disponibilidad y requisitos de ubicación.

La implementación tendrá al menos un sitio central (también llama a un centro de datos, esto es un centro de datos para todos los servidores que se encuentra en ella), y tendrá cada sitio central en la implementación de un servidor Standard Edition o al menos un grupo de servidores Front-End de Enterprise Edition. A continuación señalamos las diferencias de cada opción:

- Servidor Standard Edition incluye una base de datos de SQL Server Express instalada.

- Grupo de servidores Front-End de Enterprise Edition incluye:

  - Uno o varios servidores Front-End (lo ideal sería que al menos tres, para escalabilidad), con un máximo de doce. Puede que se necesite equilibrio de carga para más de un servidor.

  - Un independiente servidor Back-End.

Un poco más avanzada esta sección encontrará más información sobre los distintos roles de servidor.

Además de los sitios centrales, puede acabar tener uno o varios sitios de sucursal asociados con el sitio central. Dependen en el sitio central para casi toda su funcionalidad, por lo tanto ¿cuáles son las que formada, exactamente?

- Aplicación con funciones de supervivencia de sucursal, que combina una puerta de enlace de telefónica conmutada (RTC) de la red, con algunas Skype para la funcionalidad del servidor de negocio.

- Servidor de sucursal con funciones de supervivencia, es un servidor que ejecuta Windows Server que tenga Skype para Business Server registrador y el software de servidor de mediación instalado.

- Puerta de enlace RTC independiente (que no forma parte de la aplicación de sucursal con funciones de supervivencia).

- Servidor de mediación independiente o grupo de servidores de mediación independiente (si no desea combinar esta función con la aplicación de sucursal con funciones de supervivencia).

## <a name="whats-in-a-skype-for-business-server-site"></a>¿Qué es un Skype para sitio de Business Server?

Para obtener más detalles, también puede tener un sitio central:

- Varios grupos de Front-End, en el mismo dominio o en dominios diferentes (Recuerde que en la planeación de que todos los servidores Front-End en un grupo de servidores Front-End, junto con los servidores Back-End para el grupo de servidores, tienen que estar en el mismo dominio).

- Varios servidores Standard Edition.

- Office Web Apps Server, que se usa con Office Web Apps en Skype para Business Server para el uso compartido y la representación de presentaciones de PowerPoint.

- Servidor perimetral o grupo perimetral (en una red perimetral). Son necesarios si quiere que la implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace Extensible Messaging and Presence Protocol (XMPP) y el acceso de usuarios remotos. Encontrará más detalles en la documentación de planeación del servidor perimetral.

- Servidor de Chat persistente. Resulta útil si quiere que los usuarios puedan participar en conversaciones entre varias entidades sobre un tema en particular que persisten en el tiempo. Hay más información en la planeación de tema de servidor de Chat persistente.

- Supervisión. Utiliza para admitir la recolección de datos de audio y vídeo (A / V) calidad de la experiencia (QoE) y llamada de detalles del registro (CDR) para Enterprise Voice y / conferencias de A/v en su implementación. Nos detendremos en esto en el tema de planeación de la supervisión.

- Director o grupo de directores. No es necesario, pero útil si desea mejorar la resistencia y habilitar la redirección de Skype para las solicitudes de usuario empresarial grupo principal del usuario. Si desea implementar directores, se admite un máximo de 10 por grupo de servidores. Si se trata de algo que necesita, definitivamente seguir leyendo en la planeación de tema de directores.

- Proxy inverso. Esto no es un Skype para el componente de servidor empresarial, pero si desea admitir el uso compartido de contenido web para los usuarios federados, si va a admitir el tráfico de movilidad, si desean que los usuarios remotos usar la libreta de direcciones, participación en reuniones y así sucesivamente, esto es algo aquí ¿desea tener en su entorno. No hay una configuración de seguridad de tema de servidor proxy inverso que desproteger para obtener más detalles, cuando esté listo.

A continuación encontrará más información sobre cómo combinar estos servidores.

Todos los grupos de servidores Front-End y servidores Standard Edition implementados en el sitio central compartan lo siguiente, suponiendo que haya implementado en ellos:

||||
|:-----|:-----|:-----|
|Director o grupo de directores  <br/> |Servidor de mediación independiente o grupo de servidores de mediación  <br/> |Servidor Office Web Apps  <br/> |
|Servidor perimetral o grupo perimetral  <br/> |Grupo de servidor de conversaciones o servidor de Chat persistente persistente  <br/> |Supervisión  <br/> |

¿Dónde está el servidor de mensajería unificada de Exchange (UM) en esta lista? Bueno, sin duda usarlo con Skype para Business Server si desea integrar con mensajería unificada de Exchange, pero no es un componente de la Skype para sitio de Business Server, por lo que nos estamos mencionar aquí no.

Es posible que se planea tener varios sitios central y, si es así, pueden compartir los siguientes servidores y roles, si estén implementados en el sitio central:

|||
|:-----|:-----|
|Servidor de mediación independiente o grupo de servidores de mediación  <br/> |Servidor perimetral o grupo perimetral  <br/> |
|Grupo de servidor de conversaciones o servidor de Chat persistente persistente  <br/> |Supervisión  <br/> |

Al igual que la última lista, se no hemos incluido la Exchange servidor de mensajería unificada aquí porque no es parte de la Skype para la implementación de servidor empresarial, pero ésta se encuentra en la misma categoría aquí, demasiado.

Evidentemente, hay otros componentes y opciones que se incluyen en las implementaciones.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |Puertas de enlace RTC (si implementa Telefonía IP empresarial)  <br/> |Exchange servidor de mensajería unificada (si desea integrar con mensajería unificada de Exchange)  <br/> |Equilibrio de carga de DNS  <br/> |
|Equilibradores de carga de hardware  <br/> |Bases de datos de SQL Server  <br/> |Recursos compartidos de archivos  <br/> ||

## <a name="server-roles"></a>Roles de servidor

Cada servidor que ejecuta Skype para Business Server ejecuta uno o varios roles de servidor. Un rol de servidor es un conjunto definido de Skype para funcionalidades de Business Server proporcionado por ese servidor. No es necesario implementar todos los roles del servidor disponibles en su red. Instale solo los que incluyan la funcionalidad que desee.

Para la mayoría de roles del servidor, puede implementar grupos de varios servidores que ejecuten el mismo rol del servidor para, así, obtener una mayor escalabilidad y alta disponibilidad. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Para la mayoría de los tipos de grupos de servidores de Skype para Business Server, debe implementar un equilibrador de carga para distribuir el tráfico entre los diversos servidores del grupo de servidores. Skype para Business Server es compatible con equilibrio de carga de sistema de nombres de dominio (DNS) y los equilibradores de carga de hardware.

### <a name="front-end-server-and-back-end-server"></a>Servidor front-end y servidor back-end

En Skype para Business Server Enterprise Edition, el servidor Front-End es la función de servidor principal y se ejecuta muchas Skype básica para las funciones de servidor empresarial. El servidor Front-End, junto con los servidores Back-End, son las funciones de servidor sólo es necesarias que en cualquier Skype para la implementación de Business Server Enterprise Edition.

Un grupo de servidores Front-End es un conjunto de servidores Front-End, configurados de manera idéntica, que funcionan conjuntamente para proporcionar servicios para un grupo de usuarios comunes. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.

El servidor Front-End incluye lo siguiente:

- Registro y autenticación de usuarios.

- Información de presencia e intercambio de tarjetas de contacto.

- Servicios de libreta de direcciones y ampliación de la lista de distribución.

- Funcionalidad de MI, incluidas las conferencias de MI de varios participantes.

- Conferencia web, conferencia de acceso telefónico local por RTC y conferencia A/V (si se ha implementado).

- Aplicación Servicios de hospedaje para dos aplicaciones incluidas con Skype para Business Server (por ejemplo, aplicación operador de conferencia y el grupo de respuesta) y aplicaciones de otros fabricantes.

- Opcionalmente, la supervisión, para recopilar información de uso en forma de registros detallados de llamadas (CDR) y registros de errores de llamadas (CER). Esta información proporciona métricas sobre la calidad de los medios (audio y vídeos) recorrido de la red para las llamadas de telefonía IP empresarial y A / conferencias A/v.

- Componentes web para las tareas basadas en web compatibles, como el Programador web y el Iniciador de participación en reuniones.

- Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para obtener información detallada, consulte [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) en la documentación de planeación.

    En Lync Server 2010 y versiones anteriores, la supervisión y archivado eran roles de servidor independiente, que no se instala en el servidor Front-End.

- Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.

Los grupos de servidores front-end también son el lugar principal de almacenamiento de los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de esta información en los servidores back-end.

Además, un servidor de Front-End en la implementación también se ejecuta el servidor de Administración Central, que administra y distribuye los datos de configuración básica para todos los servidores que ejecutan Skype para Business Server. El servidor de Administración Central también proporciona el Shell de administración de Lync Server y las capacidades de transferencia de archivo.

Los servidores Back-End son los servidores de base de datos que ejecuta Microsoft SQL Server que proporcionan los servicios de base de datos para el grupo de servidores Front-End. Los servidores Back-End servir como almacenes de copia de seguridad para el usuario y los datos de la conferencia del grupo de servidores y son los almacenes principales para otras bases de datos como la base de datos de grupo de respuesta. Puede tener un único servidor Back-End, pero se recomienda [servidor Back-End de alta disponibilidad en Skype para Business Server](../high-availability-and-disaster-recovery/back-end-server.md) para la conmutación por error. Servidores de Back-End no ejecute cualquier Skype para software de servidor empresarial.

> [!IMPORTANT]
> No se recomienda al instalar Skype para bases de datos de Business Server con otras bases de datos. Si lo hace, disponibilidad y el rendimiento pueden verse afectados.

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. Los métodos de agrupación en clústeres de conmutación por error de grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL son preferidos con Skype para Business Server 2019.

La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.

### <a name="edge-server"></a>Servidor perimetral

Servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios de fuera de los servidores de seguridad de la organización. Estos usuarios externos pueden incluir los usuarios de la organización que actualmente están fuera del sitio de trabajo, los usuarios de organizaciones de socios federados y usuarios externos que han sido invitados a participar en conferencias hospedadas en su Skype para la implementación de Business Server.

Implementar servidor perimetral también permite a los servicios de movilidad, que admite la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden usar dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Además, los dispositivos móviles admiten algunas características de Enterprise Voice, por ejemplo, haga clic para unirse a una conferencia, llamada vía trabajo, el uso de un solo número, correo de voz y llamadas perdidas. La característica de movilidad también admite las notificaciones de inserción en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.

Los servidores perimetrales también incluyen un proxy totalmente integrado de Extensible Messaging and Presence Protocol (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para habilitar su Skype para los usuarios de Business Server permite agregar contactos de socios basados en XMPP para mensajería instantánea y presencia.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019. Para obtener más información, vea [la federación XMPP migrar](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>Servidor de mediación

Servidor de mediación es un componente necesario para la implementación de Enterprise Voice, llamadas vía trabajo y conferencia de acceso telefónico. Servidor de mediación traduce señalización y, en algunas configuraciones, medios entre su Skype interno para la infraestructura de Business Server y conmutada puerta de enlace de red (RTC) de teléfono, IP-PBX o un tronco de protocolo de inicio de sesión (SIP). Puede ejecutar el servidor de mediación combinado en el mismo servidor como servidor Front-End o dividirse en un grupo de servidores de mediación independiente.

Para obtener información detallada, consulte [componente del servidor de mediación en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Servidor de interoperabilidad de vídeo

Vídeo de interoperabilidad de servidor es una función nueva a partir de Skype para Business Server 2015. Permite integrar su Skype para la implementación de servidor empresarial con determinadas soluciones de terceros VTC (sistema de teleconferencia de vídeo). Un respecto actúa como intermediario entre un sistema de teleconferencia parte 3ª y un Skype para la implementación de Business Server. En esta versión, el VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco o Tandberg.

Para obtener información detallada, consulte [Plan para servidor de interoperabilidad de vídeo de Skype para Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Los directores pueden autenticar Skype para las solicitudes de usuario Business Server, pero no se encarga de las cuentas de usuario o proporcionar presencia o servicios de conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones donde el acceso de usuarios externos está permitido. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no llega los servidores front-end.

### <a name="persistent-chat-server-roles"></a>Roles de servidor de Chat en grupo

> [!NOTE]
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.

El chat persistente permite a los usuarios participar en conversaciones entre varias entidades sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente, mientras que el servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.

Los servidores que ejecutan Skype para Business Server Standard Edition también se puede ejecutar el chat persistente se colocan en el mismo servidor. No se puede combinar el Persistent Chat servidor Front-End con servidor Front-End de Enterprise Edition.

Para obtener información detallada, consulte [Plan for Persistent Chat Server en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Compatibilidad entre la alta disponibilidad y la recuperación ante desastres

Skype para Business Server proporciona una alta disponibilidad mediante la redundancia de servidores a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.

Skype para Business Server también proporciona ante desastres medidas de recuperación mediante la habilitación de emparejamiento de grupo de servidores. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.

Skype para Business Server también admite varias opciones para una alta disponibilidad de servidor Back-End. Estos son los siguientes:

- Creación de reflejo de la base de datos

- Grupos de disponibilidad AlwaysOn

- Instancias de clúster de conmutación por error de AlwaysOn (FCI)

- Clústeres de conmutación por error de SQL

Para obtener información detallada sobre el apareamiento de grupo de servidores y alta disponibilidad de servidor Back-End, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Combinación de servidor en Skype para Business Server

Hemos usado el término combinar ya, pero ¿qué significa esto? Skype para Business Server permite localizar algunos roles de servidor y características en el mismo servidor, que es la combinación, o en servidores diferentes, pero puede resultar confusa cuando está iniciándose a, y si está realizando un servidor Standard Edition o Enterprise Edition implementación (cada uno de ellos se incluyen con sus propias normas). Para ayudar con la planeación, incluimos combinación de servidor en implementaciones de servidor de Standard Edition y las implementaciones de grupo de servidores Front-End de Enterprise Edition (en la mayoría de los casos, esta información es idéntica y donde es diferente, se llama específicamente).

### <a name="collocation-of-server-roles"></a>Combinación de roles del servidor

El servidor Standard Edition tiene la siguiente función combinado (se requiere configuración adicional aunque), mientras se encuentra en el grupo de servidores Front-End de Enterprise Edition, este rol se puede combinar, o implementada en un servidor independiente:

- Mediación

Estos roles del servidor se tienen que implementar en un servidor separado:

- Director

- Perimetral

- Servidor de interoperabilidad de vídeo

- Office Web Apps

### <a name="databases"></a>Bases de datos

Esto es el área con reales diferencias entre las implementaciones de servidores Standard Edition y las implementaciones de Enterprise Edition server grupo de servidores, por lo que tendremos dos secciones siguientes, seguido de algunas reglas adicionales para ambos.

#### <a name="standard"></a>Standard

Dado que SQL Server Express está combinado en el servidor Standard Edition y no se puede mover, esto es bastante sencillo. Además, si implementa el servidor de Chat persistente en un servidor Standard Edition, también le permite combinar la base de datos de cumplimiento de normas de Chat persistente en el servidor Standard Edition y el Chat persistente demasiado, pero no es necesario.

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

Estos no se pueden combinar en el servidor Standard Edition, pero pueden ir en un servidor de base de datos única de sus propios:

- Base de datos de supervisión

- Base de datos de archivado

- Cualquier base de datos back-end para un grupo de servidores Front-End de Enterprise Edition

#### <a name="enterprise"></a>Enterprise

Las siguientes bases de datos se pueden instalar en el mismo back-end SQL Server:

- Base de datos back-end

- Base de datos de supervisión

- Base de datos de archivado

- Base de datos de Chat persistente

- Base de datos de cumplimiento de normas de Chat persistente

#### <a name="both"></a>Ambos

Ahora, hay algunas reglas adicionales que se deben seguir al combinar Skype para bases de datos de Business Server en una sola instancia SQL, o en varias instancias SQL en la misma base de datos de SQL Server:

- Cada instancia de SQL sólo puede contener una base de datos back-end único para un grupo de servidores Front-End de Enterprise Edition, una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos Chat persistente y una sola Chat persistente cumplimiento base de datos.

- El servidor de base de datos no es compatible con más de un grupo de servidores Front-End de Enterprise Edition, un servidor que ejecuta el servidor de archivado, un servidor que ejecuta la supervisión, una sola base de datos Chat persistente y una sola Chat persistente cumplimiento base de datos, pero puede admitir uno de cada uno, independientemente de si las bases de datos usan la misma instancia de SQL Server o distintas instancias de SQL Server.

    > [!NOTE]
    > Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.

### <a name="file-shares"></a>Recursos compartidos de archivos

El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:

- Servidor de base de datos, incluidos el servidor Back-End de un grupo de servidores Front-End de Enterprise Edition

- Base de datos de supervisión

- Base de datos de archivado

- Base de datos de Chat persistente

- Base de datos de cumplimiento de normas de Chat persistente

> [!CAUTION]
> Tenga en cuenta que, si bien puede colocar el recurso compartido de archivos en estos servidores, es fundamental que tenga en cuenta que no lo recomendamos. Si ha colocado el recurso compartido de archivos con cualquier otro rol de servidor, asegúrese de que está supervisando el espacio en disco y los problemas de rendimiento de forma periódica.

### <a name="keep-in-mind"></a>Recordatorio

- No se puede combinar un servidor proxy inverso, que no es un Skype para el componente de servidor empresarial y no puede ser incluso en su topología. Si desea admitir el uso compartido de contenido web para los usuarios federados, entre muchas otras cosas, necesitará a un proxy inverso. Si necesita, vamos a implementar la compatibilidad con proxy inverso para Skype Business Server mediante la configuración de un servidor proxy inverso existente que ya está en la organización que se va a usar mediante otras aplicaciones.

- No se puede combinar ningún componente de mensajería unificada de Exchange ni SharePoint Server con cualquier Skype para el rol de servidor empresarial.

## <a name="see-also"></a>Vea también

[Topologías de referencia de Skype para Business Server](reference-topologies.md)