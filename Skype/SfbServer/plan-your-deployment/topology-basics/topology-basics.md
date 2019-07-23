---
title: Conceptos básicos sobre la topología de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumen: Elija su topología para Skype empresarial Server. Obtenga más información sobre Server collocation para Skype empresarial Server.'
ms.openlocfilehash: 00154c754292fd960942f0f0da7f95bb6b5b1c19
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "35820995"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Conceptos básicos sobre la topología de Skype empresarial Server

**Resumen:** Elija su topología para Skype empresarial Server. Obtenga más información sobre Server collocation para Skype empresarial Server.

Antes de prepararse, debe saber que está planificando la topología adecuada para su implementación de Skype empresarial Server. Lo primero que debe decidir es si va a tener una implementación local de Skype empresarial Server, o si va a combinarlo con una implementación en línea de Skype empresarial Server en una implementación híbrida de Skype empresarial. En ambos casos, deseará leer más, ya que detallamos las topologías locales aquí, pero los detalles híbridos se documentan en su propia sección.

También puede ver algunas topologías de ejemplo en las topologías de [referencia de Skype empresarial Server](reference-topologies.md).

## <a name="sites"></a>Sitios

En Skype empresarial Server, se definen los sitios de la red que contienen los componentes de Skype empresarial Server. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que los sitios de Skype empresarial Server son un concepto independiente de los sitios de los servicios de dominio de Active Directory y los sitios de Microsoft Exchange Server. Los sitios de Skype empresarial Server no necesitan corresponderse con los sitios de Active Directory.

Skype empresarial Server admite la implementación local de uno o varios sitios que se pueden escalar según los requisitos de ubicación y disponibilidad alta.

Su implementación tendrá al menos un sitio central (también denominado Centro de proceso de aplicaciones, este es un centro de recursos para todos los servidores ubicados en él) y cada sitio central de la implementación tendrá un servidor Standard Edition o al menos un grupo de servidores front-end Enterprise Edition. A continuación señalamos las diferencias de cada opción:

- El servidor Standard Edition incluye una base de datos de SQL Server Express.

- El grupo de servidores front-end Enterprise Edition incluye:

  - Uno o más servidores front-end (idealmente, como mínimo, tres, por escalabilidad), con un máximo de doce. Puede que se necesite equilibrio de carga para más de un servidor.

  - Un servidor back-end independiente.

Un poco más avanzada esta sección encontrará más información sobre los distintos roles de servidor.

Además de sus sitios centrales, también puede acabar de tener uno o más sitios de sucursal asociados con su sitio central. Dependen del sitio central para casi toda su funcionalidad, por lo que son exactamente lo que componen.

- Dispositivo de rama superviviente, que combina una puerta de enlace de red de telefonía pública conmutada (RTC), con alguna funcionalidad de Skype empresarial Server.

- Servidor de sucursal superviviente, es un servidor que ejecuta Windows Server y tiene instalado el software de servidor de mediación y el registrador de Skype empresarial Server.

- Puerta de enlace independiente de RTC (que no forma parte de la aplicación de rama superviviente).

- Servidor de mediación independiente o grupo de servidores de mediación independiente (si no quiere Collocate esta función con el dispositivo de sucursal superviviente).

## <a name="whats-in-a-skype-for-business-server-site"></a>¿Qué hay en un sitio de Skype empresarial Server?

Para obtener más detalles, un sitio central también puede tener:

- Varios grupos front-end, en el mismo dominio o en dominios diferentes (Recuerde que, al planear que todos los servidores front-end de un grupo de servidores front-end, junto con los servidores back-end de la agrupación, tengan que estar en el mismo dominio).

- Varios servidores Standard Edition.

- Office Web Apps Server, que se usa con Office Web Apps en Skype empresarial Server para compartir y representar presentaciones de PowerPoint.

- Servidor perimetral o grupo perimetral (en una red perimetral). Son necesarios si quiere que la implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace Extensible Messaging and Presence Protocol (XMPP) y el acceso de usuarios remotos. Puede encontrar más información en la documentación de planeación del servidor perimetral.

- Servidor de chat persistente. Resulta útil si quiere que los usuarios puedan participar en conversaciones entre varias entidades sobre un tema en particular que persisten en el tiempo. Encontrará más información en el tema planear el servidor de chat persistente.

- Supervisión. Se usa para admitir la recopilación de datos de la calidad de la experiencia de la experiencia de audio/vídeo (A/V) y la grabación de detalles de llamadas (CDR) de las conferencias de telefonía IP empresarial y A/V de su implementación. Nos detendremos en esto en el tema de planeación de la supervisión.

- Grupo de directores o directores. No es necesario, pero es útil si desea mejorar la resiliencia y habilitar el redireccionamiento de las solicitudes de usuario de Skype empresarial al grupo de hogar del usuario. Si desea implementar directores, se admite un máximo de 10 por grupo. Si es algo que necesita, siga leyendo de forma definitiva en el tema Planning for Directors.

- Proxy inverso. Este no es un componente de Skype empresarial Server, pero si desea permitir el uso compartido de contenido web para usuarios federados, si tiene previsto admitir tráfico de movilidad, si los usuarios remotos desean usar la libreta de direcciones, unirse a reuniones, etc., esto es algo que le desea tener en su entorno. Hay un tema de configuración del servidor proxy inverso que puedes consultar para obtener más información, cuando estés listo.

A continuación encontrará más información sobre cómo combinar estos servidores.

Todos los grupos de aplicaciones para el usuario y los servidores Standard Edition implementados en su sitio central comparten lo siguiente, suponiendo que los haya implementado:

||||
|:-----|:-----|:-----|
|Grupo de directores o directores  <br/> |Servidor de mediación independiente o grupo de servidores de mediación  <br/> |Servidor Office Web Apps  <br/> |
|Servidor perimetral o grupo Edge  <br/> |Servidor de chat persistente o grupo de servidores de chat persistente  <br/> |Supervisión  <br/> |

¿Dónde está la mensajería unificada de Exchange en esta lista? Bueno, puede utilizarlo con Skype empresarial Server si desea integrarlo con la mensajería unificada de Exchange, pero no es un componente del sitio de Skype empresarial Server, por lo que no lo mencionaremos aquí.

Es posible que esté planeando tener varios sitios centrales y, si es así, puedan compartir los siguientes servidores y roles, si se han implementado en su sitio central:

|||
|:-----|:-----|
|Servidor de mediación independiente o grupo de servidores de mediación  <br/> |Servidor perimetral o grupo Edge  <br/> |
|Servidor de chat persistente o grupo de servidores de chat persistente  <br/> |Supervisión  <br/> |

Al igual que la última lista, no incluimos el servidor de mensajería unificada de Exchange aquí porque no forma parte de la implementación de Skype empresarial Server, sino que también cae en la misma categoría.

Evidentemente, hay otros componentes y opciones que se incluyen en las implementaciones.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |Puertas de enlace RTC (si implementa Telefonía IP empresarial)  <br/> |Servidor de mensajería unificada de Exchange (si desea integrar con mensajería unificada de Exchange)  <br/> |Equilibrio de carga de DNS  <br/> |
|Equilibradores de carga de hardware  <br/> |Bases de datos de SQL Server  <br/> |Recursos compartidos de archivos  <br/> ||

## <a name="server-roles"></a>Roles de servidor

Cada servidor que ejecuta Skype empresarial Server ejecuta uno o varios roles de servidor. Un rol de servidor es un conjunto definido de funcionalidades de Skype empresarial Server proporcionadas por ese servidor. No es necesario implementar todos los roles del servidor disponibles en su red. Instale solo los que incluyan la funcionalidad que desee.

Para la mayoría de roles del servidor, puede implementar grupos de varios servidores que ejecuten el mismo rol del servidor para, así, obtener una mayor escalabilidad y alta disponibilidad. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Para la mayoría de los tipos de grupos en Skype empresarial Server, debe implementar un equilibrador de carga para distribuir el tráfico entre los distintos servidores del grupo. Skype empresarial Server admite los equilibradores de carga de hardware y el equilibrio de carga del sistema de nombres de dominio (DNS).

### <a name="front-end-server-and-back-end-server"></a>Servidor front-end y servidor back-end

En Skype empresarial Server Enterprise Edition, el servidor front-end es el rol de servidor principal y ejecuta muchas funciones básicas de Skype empresarial Server. El servidor front-end, junto con los servidores back-end, son los únicos roles de servidor que se requieren en cualquier implementación de Skype empresarial Server Enterprise Edition.

Un grupo front-end es un conjunto de servidores front-end, configurado de manera idéntica, que funcionan conjuntamente para proporcionar servicios a un grupo común de usuarios. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.

El servidor front-end incluye lo siguiente:

- Registro y autenticación de usuarios.

- Información de presencia e intercambio de tarjetas de contacto.

- Servicios de libreta de direcciones y ampliación de la lista de distribución.

- Funcionalidad de MI, incluidas las conferencias de MI de varios participantes.

- Conferencia web, conferencia de acceso telefónico local por RTC y conferencia A/V (si se ha implementado).

- Hospedaje de aplicaciones para las aplicaciones incluidas con Skype empresarial Server (por ejemplo, el operador de conferencia y la aplicación de grupo de respuesta) y las aplicaciones de terceros.

- Opcionalmente, la supervisión, para recopilar información de uso en forma de registros detallados de llamadas (CDR) y registros de errores de llamadas (CER). Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) que atraviesan tu red tanto las llamadas de voz empresariales como las conferencias A/V.

- Componentes web para las tareas basadas en web compatibles, como el Programador web y el Iniciador de participación en reuniones.

- Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para ver más detalles, mire [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) en la documentación de planeación.

    En Lync Server 2010 y versiones anteriores, la supervisión y el archivado eran roles de servidor diferentes, no colocados en el servidor front-end.

- Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.

Los grupos de servidores front-end también son el lugar principal de almacenamiento de los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de esta información en los servidores back-end.

Además, un servidor front-end de la implementación también ejecuta el servidor de administración central, que administra e implementa los datos de configuración básica de todos los servidores que ejecutan Skype empresarial Server. El servidor de administración central también proporciona capacidades de Shell de administración y transferencia de archivos de Lync Server.

Los servidores back-end son servidores de base de datos que ejecutan Microsoft SQL Server y que proporcionan los servicios de base de datos para el grupo de servidores front-end. Los servidores back-end actúan como almacenes de copia de seguridad del usuario del grupo y los datos de la Conferencia, y son las principales tiendas de otras bases de datos, como la base de datos de grupos de respuesta. Puede tener un único servidor de servicios de fondo, pero se recomienda usar la [alta disponibilidad del servidor de servicios de fondo en Skype empresarial Server](../high-availability-and-disaster-recovery/back-end-server.md) para la conmutación por error. Los servidores back-end no ejecutan ningún software de servidor de Skype empresarial.

> [!IMPORTANT]
> No recomendamos collocating bases de datos de Skype empresarial Server con otras bases de datos. Si lo hace, la disponibilidad y el rendimiento pueden verse afectados.

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.

La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.

### <a name="edge-server"></a>Servidor perimetral

El servidor perimetral permite a los usuarios comunicarse y colaborar con usuarios ajenos a los firewalls de la organización. Estos usuarios externos pueden incluir los usuarios de la organización que actualmente están trabajando fuera del sitio, los usuarios de organizaciones de socios federados y los usuarios externos que han recibido una invitación para unirse a conferencias hospedadas en su implementación de Skype empresarial Server.

La implementación de servidor perimetral también permite servicios de movilidad, que admiten la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden usar dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y llamadas perdidas. La característica de movilidad también admite las notificaciones de inserción en los dispositivos móviles que no son compatibles con las aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.

Los servidores perimetrales también incluyen un proxy totalmente integrado de Extensible Messaging and Presence Protocol (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para permitir que los usuarios de Skype empresarial Server agreguen contactos de socios basados en XMPP para la mensajería instantánea y la presencia.

> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte migrar la [Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>Servidor de mediación

Servidor de mediación es un componente necesario para implementar la telefonía IP empresarial, la llamada a través del trabajo y las conferencias de acceso telefónico local. Servidor de mediación traduce la señalización y, en algunas configuraciones, multimedia entre su infraestructura interna de Skype empresarial Server y una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un tronco de protocolo de inicio de sesión (SIP). Puede ejecutar el servidor de mediación en el mismo servidor que el servidor front-end o separarlo en un grupo de servidores de mediación independiente.

Para obtener más información, consulte [componente de servidor de mediación en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Servidor de interoperabilidad de vídeo

El servidor de interoperabilidad de vídeo es un nuevo rol a partir de Skype empresarial Server 2015. Le permite integrar su implementación de Skype empresarial Server con determinadas soluciones de VTC (sistema de videoconferencias de terceros). Una acción de VIS es un intermediario entre un sistema de teleconferencia de terceros y una implementación de Skype empresarial Server. En esta versión, el VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco o Tandberg.

Para obtener más información, consulte [planear el servidor de interoperabilidad de vídeo en Skype empresarial Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Director

Los directores pueden autenticar solicitudes de usuario de Skype empresarial Server, pero no alojan cuentas de usuario ni proporcionan servicios de presencia o de conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones donde el acceso de usuarios externos está permitido. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no llega los servidores front-end.

### <a name="persistent-chat-server-roles"></a>Roles de servidor de chat persistentes

> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.

El chat persistente permite a los usuarios participar en conversaciones entre varias entidades sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente, mientras que el servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.

Los servidores que ejecutan Skype empresarial Server Standard Edition también pueden ejecutar una conversación persistente colocada en el mismo servidor. No puede Collocate el servidor front-end de chat persistente con el servidor front-end Enterprise Edition.

Para obtener más información, vea [planear el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Compatibilidad de alta disponibilidad y recuperación ante desastres

Skype empresarial Server ofrece alta disponibilidad por redundancia de servidores a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.

Skype empresarial Server también proporciona medidas de recuperación ante desastres mediante la habilitación del emparejamiento de grupos. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.

Skype empresarial Server también admite varias opciones para la alta disponibilidad del servidor back-end. Estos son los siguientes:

- Creación de reflejo de la base de datos

- Grupos de disponibilidad AlwaysOn

- Instancias de clúster de conmutación por error de AlwaysOn (FCI)

- Clústeres de conmutación por error de SQL

Para obtener más información sobre el emparejamiento de grupos y el servidor de servicios de fondo alta disponibilidad, consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Collocation de servidor en Skype empresarial Server

Ya hemos usado el término Collocate, pero ¿qué significa esto? Skype empresarial Server le permite ubicar algunos roles de servidor y características en el mismo servidor, que es collocation, o en servidores diferentes, pero puede resultar confuso al empezar y si está haciendo un servidor Standard Edition o Enterprise Edition implementación (cada una de ellas viene con sus propias reglas). Para ayudarle con su planeamiento, incluimos la collocation del servidor en las implementaciones del servidor Standard Edition y las implementaciones del grupo de aplicaciones para el usuario de Enterprise Edition (en la mayoría de los casos esta información es idéntica, y cuando es diferente, se lo llama específicamente).

### <a name="collocation-of-server-roles"></a>Combinación de roles del servidor

El servidor Standard Edition tiene la siguiente función colocada (aunque es necesaria una configuración adicional), mientras que en el grupo de servidores front-end Enterprise Edition, este rol se puede dar o implementar en un servidor independiente:

- Mediación

Estos roles del servidor se tienen que implementar en un servidor separado:

- Director

- Perimetral

- Servidor de interoperabilidad de vídeo

- Office Web Apps

### <a name="databases"></a>Bases de datos

Este es el área con diferencias reales entre las implementaciones del servidor Standard Edition y las implementaciones del grupo de servidores Enterprise Edition, por lo que tendremos dos secciones, seguidas de algunas reglas adicionales para ambas.

#### <a name="standard"></a>Standard

Puesto que SQL Server Express se encuentra en el servidor Standard Edition y no se puede mover, esto es bastante sencillo. Además, si implementas un servidor de chat persistente en un servidor Standard Edition, también puedes Collocate el chat persistente y la base de datos de cumplimiento de chat persistente en el servidor Standard Edition, pero no es necesario.

> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.

Estas no se pueden incluir en el servidor Standard Edition, pero pueden ir en un único servidor de base de datos propio:

- Base de datos de supervisión

- Base de datos de archivado

- Cualquier base de datos back-end para un grupo de servidores front end Enterprise Edition

#### <a name="enterprise"></a>Enterprise

Las siguientes bases de datos se pueden colocar en el mismo servidor SQL Server back-end:

- Base de datos back-end

- Base de datos de supervisión

- Base de datos de archivado

- Base de datos de chat persistente

- Base de datos de cumplimiento de chat persistente

#### <a name="both"></a>Both

Ahora, hay algunas reglas adicionales que puede seguir al collocating de las bases de datos de Skype empresarial Server en una única instancia de SQL o en varias instancias de SQL en la misma base de datos de SQL Server:

- Cada instancia de SQL puede contener una única base de datos de back-end para un grupo de servidores front end Enterprise Edition, una única base de datos de supervisión, una única base de datos de archivado, una única base de datos de chat persistente y una única base de datos de cumplimiento persistente.

- El servidor de base de datos no es compatible con más de un grupo de servidores front-end Enterprise Edition, un servidor que ejecuta el archivado, un servidor que ejecuta supervisión, una base de datos de chat persistente y una única base de datos de cumplimiento persistente, pero puede admitir una de cada uno. independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias independientes de SQL Server.

    > [!NOTE]
    > Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.

### <a name="file-shares"></a>Recursos compartidos de archivos

El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:

- Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front end Enterprise Edition

- Base de datos de supervisión

- Base de datos de archivado

- Base de datos de chat persistente

- Base de datos de cumplimiento de chat persistente

> [!CAUTION]
> Tenga en cuenta que, si bien puede colocar el recurso compartido de archivos en estos servidores, es fundamental que tenga en cuenta que no lo recomendamos. Si collocating el uso compartido de archivos con cualquier otro rol de servidor, asegúrese de que está supervisando los problemas de espacio en disco y rendimiento de forma periódica.

### <a name="keep-in-mind"></a>Recordatorio

- No puede Collocate un servidor proxy inverso, que no es un componente de Skype empresarial Server, y es posible que ni siquiera esté en su topología. Necesitará un proxy inverso si desea permitir el uso compartido de contenido web para usuarios federados, entre muchas otras cosas. Si es necesario, para implementar un servidor proxy inverso existente que ya esté en su organización y que esté usando otras aplicaciones, debe configurar un servidor proxy inverso existente que ya esté en su organización.

- No puede Collocate ningún componente de mensajería unificada de Exchange o componente de servidor de SharePoint con ningún rol de servidor de Skype empresarial.

## <a name="see-also"></a>Vea también

[Topologías de referencia para Skype empresarial Server](reference-topologies.md)
