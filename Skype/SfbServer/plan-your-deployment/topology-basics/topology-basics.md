---
title: Conceptos básicos de topología de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumen: Elegir la topología para Skype para Business Server 2015. Obtenga información acerca de la colocación de servidores de Skype para Business Server 2015.'
ms.openlocfilehash: 5fbb6a490f8ba35d2e16ccbab60a17d788cb92e8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="topology-basics-for-skype-for-business-server-2015"></a>Conceptos básicos de topología de Skype Empresarial Server 2015
 
**Resumen:** elija la topología para Skype Empresarial Server 2015. Información sobre la colocación del servidor de Skype Empresarial Server 2015.
  
Antes de preparar nada, deseará saber que piensa para la topología correcta para su implementación de Skype para Business Server 2015. Lo primero que tiene que decidir es si va a tener una implementación local de Skype para Business Server 2015, o si va a combinar esto con un Skype para la implementación de servidor de negocios en línea en una implementación híbrida. En cualquier caso, va a desea leer más, como detallaremos las topologías local aquí, pero se documentan los detalles híbrido en su propia sección.
  
También puede ver algunas topologías de ejemplo en [las topologías de referencia para Skype para Business Server 2015](reference-topologies.md).
  
## <a name="sites"></a>Sitios

En Skype para Business Server, puede definir sitios en la red que contienen Skype para los componentes de Business Server. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que Skype para sitios de Business Server son un concepto independiente de los sitios de los servicios de dominio de Active Directory y Microsoft Exchange Server. No es necesario que su Skype para sitios de Business Server corresponden a los sitios de Active Directory.
  
Skype para Business Server 2015 es compatible con la implementación local de uno o más sitios que se pueden escalar según sus requerimientos de ubicación y de alta disponibilidad.
  
La implementación tendrá al menos un sitio central (también llamado un centro de datos, esto es un centro de datos para todos los servidores que se encuentran en ella), y cada sitio central en la implementación de un servidor Standard Edition o al menos un grupo de servidores de Front-End de Enterprise Edition. A continuación señalamos las diferencias de cada opción:
  
- Servidor Standard Edition incluye una base de datos de SQL Server Express colocada.
    
- Grupo de servidores Front-End de Enterprise Edition incluye:
    
  - Uno o más servidores frontales (lo ideal sería que al menos tres, de escalabilidad), con un máximo de doce. Puede que se necesite equilibrio de carga para más de un servidor.
    
  - Un nuevo extremo servidor independiente.
    
Un poco más avanzada esta sección encontrará más información sobre los distintos roles de servidor.
  
Además de los sitios centrales, también puede terminar con uno o más sitios de sucursales asociados al sitio central. Dependen en el sitio central para casi toda su funcionalidad, así que ¿cuáles son compone de, exactamente?
  
- Que sobreviven dispositivo de bifurcación, que combina una puerta de enlace de telefónica pública conmutada (PSTN) de la red, con algunos Skype para la funcionalidad de servidor de negocios 2015.
    
- Servidor de sucursal que sobreviven, es un servidor que ejecute Windows Server que tenga Skype para Registrar 2015 de Business Server y servidor de mediación software instalado.
    
- Puerta de enlace PSTN independiente (que no forma parte del equipo de sucursal que sobreviven).
    
- Servidor de mediación de independiente o grupo de servidor de mediación independiente (si no desea colocar este rol con el dispositivo de la rama que sobreviven).
    
## <a name="whats-in-a-skype-for-business-server-site"></a>¿Qué es un Skype para sitio Business Server?

Para obtener más detalles, también puede tener un sitio central:
  
- Varios grupos de Front-End, en el mismo dominio o en dominios diferentes (Recuerde que en la planificación de todos los servidores frontales en una agrupación de Front-End, junto con los servidores de fondo nuevo para el grupo, deben estar en el mismo dominio).
    
- Varios servidores Standard Edition.
    
- Office Web Apps Server, que se utiliza con Office Web Apps en Skype para Business Server 2015 para compartir y representación de presentaciones de PowerPoint.
    
- Grupo de servidor perimetral o arista (en una red perimetral). Son necesarios si quiere que la implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace Extensible Messaging and Presence Protocol (XMPP) y el acceso de usuarios remotos. Pueden encontrarse más detalles en la documentación de planeamiento del servidor de borde.
    
- Servidor de charla persistente. Resulta útil si quiere que los usuarios puedan participar en conversaciones entre varias entidades sobre un tema en particular que persisten en el tiempo. Hay más información en la planificación para el servidor de charla persistente.
    
- Supervisión. Utiliza para admitir la recopilación de datos de audio y vídeo (A / V) calidad de experiencia (QoE) y llamada de detalle grabación (CDR) para Telefonía IP empresarial y A / conferencias en su implementación. Nos detendremos en esto en el tema de planeación de la supervisión.
    
- Director o grupo de directores. No es necesario, pero útil si desea mejorar la resiliencia y habilitar la redirección de Skype para las solicitudes de usuario Business 2015 grupo doméstico del usuario. Si desea implementar directores, se admite un máximo de 10 por cada grupo. Si se trata de algo que usted necesita, sin duda continúe leyendo Planning for tema de directores.
    
- Proxy inverso. Esto no es un Skype para el componente servidor de negocios 2015, pero si desea admitir el intercambio de contenido web para federados usuarios si desea permitir el tráfico de movilidad, si desean utilizar la libreta de direcciones que los usuarios remotos participar en reuniones y así sucesivamente, esto es algo deseará tener en su entorno. Hay un tema de servidor proxy inverso que puede consultar para obtener más detalles, cuando haya terminado de configurar.
    
A continuación encontrará más información sobre cómo combinar estos servidores.
  
Todos los grupos de Front-End y los servidores Standard Edition implementados en el sitio central compartan lo siguiente, suponiendo que haya implementado en ellos:
  
||||
|:-----|:-----|:-----|
|Director o grupo de directores  <br/> |Servidor de mediación de independiente o grupo de servidores de mediación  <br/> |Servidor Office Web Apps  <br/> |
|Servidor perimetral o borde piscina  <br/> |Grupo de Chat Server o el servidor de charla persistente persistente  <br/> |Supervisión  <br/> |
   
¿Donde es el servidor de Exchange Unified Messaging (UM) en esta lista? Bueno, ciertamente sirve con Skype para Business Server 2015 si desea integrar con mensajería unificada de Exchange, pero no es un componente de la Skype sitio servidor de negocios, por lo que nos estamos mencionar aquí no.
  
Que piensa tener varios sitio central, y si es así, pueden compartir los siguientes servidores y funciones, si está implementados en el sitio central:
  
|||
|:-----|:-----|
|Servidor de mediación de independiente o grupo de servidores de mediación  <br/> |Servidor perimetral o borde piscina  <br/> |
|Grupo de Chat Server o el servidor de charla persistente persistente  <br/> |Supervisión  <br/> |
   
Al igual que la última lista, nosotros no estamos incluyendo Exchange UM Server aquí porque no forma parte de la Skype para la implementación de Business Server 2015, pero ésta se encuentra en la misma categoría, demasiado.
  
Evidentemente, hay otros componentes y opciones que se incluyen en las implementaciones.
  
|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |Puertas de enlace RTC (si implementa Telefonía IP empresarial)  <br/> |Cambio de servidor de mensajería unificada (si desea integrar con mensajería unificada de Exchange)  <br/> |Equilibrio de carga de DNS  <br/> |
|Equilibradores de carga de hardware  <br/> |Bases de datos de SQL Server  <br/> |Recursos compartidos de archivos  <br/> ||
   
## <a name="server-roles"></a>Roles de servidor

Cada servidor que ejecuta Skype para Business Server ejecuta uno o varios roles de servidor. Un rol de servidor es un conjunto definido de Skype para funcionalidades de Business Server proporcionado por el servidor. No es necesario implementar todos los roles del servidor disponibles en su red. Instale solo los que incluyan la funcionalidad que desee.
  
Para la mayoría de los roles de servidor de alta disponibilidad y escalabilidad puede implementar grupos de varios servidores todos ejecutan el mismo rol de servidor. Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos. Para la mayoría de los tipos de grupos en Skype para Business Server, debe implementar un equilibrador de carga para distribuir el tráfico entre los distintos servidores en el grupo. Skype para Business Server es compatible con el equilibrio de carga de sistema de nombres de dominio (DNS) y equilibradores de carga hardware.
  
### <a name="front-end-server-and-back-end-server"></a>Servidor front-end y servidor back-end

En Skype para Business Server Enterprise Edition, el servidor Front-End es la función de servidor de núcleo y ejecuta muchos Skype básica para las funciones de servidor de la empresa. El servidor Front-End, junto con los servidores de fondo detrás, son los roles de servidor sólo debe ser en cualquier Skype para la implementación de Business Server Enterprise Edition. 
  
Un grupo de servidores Front-End es un conjunto de servidores frontales, configurados de forma idéntica, que trabajan juntos para ofrecer servicios a un grupo de usuarios comunes. Un grupo de varios servidores ejecutando el mismo rol proporciona escalabilidad y funciones de conmutación por error.
  
El servidor Front-End incluye lo siguiente:
  
- Registro y autenticación de usuarios.
    
- Información de presencia e intercambio de tarjetas de contacto.
    
- Servicios de libreta de direcciones y ampliación de la lista de distribución.
    
- Funcionalidad de MI, incluidas las conferencias de MI de varios participantes.
    
- Conferencia web, conferencia de acceso telefónico local por RTC y conferencia A/V (si se ha implementado).
    
- Alojamiento de aplicaciones, para aplicaciones incluidas con Skype para negocios servidor (por ejemplo, operador de conferencia y el grupo de respuesta) y aplicaciones de otros fabricantes.
    
- Opcionalmente, la supervisión, para recopilar información de uso en forma de registros detallados de llamadas (CDR) y registros de errores de llamadas (CER). Esta información proporciona métricas sobre la calidad de los medios (audio y vídeo) atravesar la red para llamadas de Telefonía IP empresarial y A / conferencias.
    
- Componentes web para las tareas basadas en web compatibles, como el Programador web y el Iniciador de participación en reuniones.
    
- Opcionalmente, el archivado, para archivar comunicaciones de MI y contenido de reuniones con fines de cumplimiento. Para obtener más información, consulte [planificación para Archiving](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) en la documentación de planificación.
    
    En Lync Server 2010 y versiones anteriores, supervisión y archivado eran diferentes roles de servidor, que no se encuentra en el servidor Front-End.
    
- Opcionalmente, si el chat persistente está habilitado, servicios web de chat persistente para la administración de salones de chat y para la carga y descarga de archivos.
    
Los grupos de servidores front-end también son el lugar principal de almacenamiento de los datos de conferencia y de usuario. La información sobre cada usuario se replica entre tres servidores front-end del grupo, y se hace una copia de seguridad de esta información en los servidores back-end.
  
Además, un servidor de Front-End de la implementación también se ejecuta el servidor de Administración Central, que administra e implementa los datos de configuración básica para todos los servidores de Skype para Business Server. El servidor de Administración Central también proporciona capacidades de transferencia de archivos y de Shell de administración de Lync Server.
  
Los servidores de fondo atrás son servidores de base de datos que ejecuta Microsoft SQL Server que proporcionan los servicios de base de datos para el grupo de servidores Front-End. Los servidores de fondo atrás sirven como almacenes de copia de seguridad para el grupo de usuarios y datos de la conferencia y son las principales tiendas para otras bases de datos como la base de datos de grupo de respuesta. Puede tener un único servidor de final de vuelta, pero se recomienda una solución que utiliza la creación de reflejos de SQL Server para failover. Servidores de Back End no ejecute cualquier Skype para software Business Server.
  
> [!IMPORTANT]
> Es recomendable colocar Skype para bases de datos de Business Server con otras bases de datos. Si lo hace, la disponibilidad y el rendimiento pueden verse afectados. 
  
La información almacenada en las bases de datos del servidor back-end incluye información de presencia, listas de contactos de los usuarios, datos de conferencia (incluidos los datos persistentes sobre el estado de todas las conferencias actuales) y datos de programación de conferencias.
  
### <a name="edge-server"></a>Servidor perimetral

Servidor perimetral permite a los usuarios comunicarse y colaborar con otros usuarios ubicados fuera de los servidores de seguridad de la organización. Los usuarios externos pueden incluir los usuarios de la organización que actualmente están fuera del sitio de trabajo, los usuarios de las organizaciones de socios federados y usuarios externos que han sido invitados a unirse a conferencias alojadas en tu Skype para la implementación de Business Server.
  
Implementar servidor perimetral también habilita los servicios de movilidad, que admite la funcionalidad de Lync en dispositivos móviles. Los usuarios pueden usar dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Además, los dispositivos móviles admiten algunas características de Telefonía IP empresarial, como hacer clic para unirse a una conferencia, llamada vía trabajo, alcance número único, correo de voz y llamadas perdidas. La característica de movilidad también admite las notificaciones de inserción para dispositivos móviles que no admiten aplicaciones que se ejecutan en segundo plano. Las notificaciones de inserción son notificaciones que se envían a dispositivos móviles sobre un evento que se produce mientras una aplicación móvil está inactiva.
  
Los servidores perimetrales también incluyen un proxy totalmente integrado de Extensible Messaging and Presence Protocol (XMPP), con una puerta de enlace XMPP incluida en los servidores front-end. Puede configurar estos componentes XMPP para habilitar su Skype para los usuarios de Business Server agregar contactos de socios de XMPP para mensajería instantánea y presencia.
  
### <a name="mediation-server"></a>Servidor de mediación

Servidor de mediación es un componente necesario para la implementación de Telefonía IP empresarial, llame a través de trabajo y conferencias de acceso telefónico. Servidor de mediación traduce la señalización y, en algunas configuraciones, medios entre su Skype para infraestructura de Business Server interno y conmutada puerta de enlace de teléfono red (conmutada PSTN), IP-PBX o un tronco de protocolo de inicio de sesión (SIP). Puede ejecutar el servidor de mediación ubicados en el mismo servidor como servidor Front-End o separados en un grupo independiente del servidor de mediación.
  
Para obtener más información, vea [componentes de servidor de mediación en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).
  
### <a name="video-interop-server"></a>Servidor de interoperabilidad de vídeo

Servidor de vídeo interoperabilidad es una nueva función de Skype para Business Server 2015. Permite integrar su Skype para la implementación de servidor de negocios con ciertas soluciones de terceros VTC (sistema de teleconferencia por vídeo). Un VIS actúa como intermediario entre un sistema de teleconferencia parte 3ª y un Skype para la implementación de Business Server. En esta versión, el VIS se centra en la interoperabilidad con los sistemas de vídeo de Cisco o Tandberg.
  
Para obtener información detallada, consulte [Plan para servidor de interoperabilidad de vídeo en Skype para Business Server 2015](../../plan-your-deployment/video-interop-server.md).
  
### <a name="director"></a>Director

Directores pueden autenticar Skype para las solicitudes del usuario Business Server, pero no las cuentas de usuario de inicio ni proporcionar presencia o servicios de conferencia. Los directores son de mucha utilidad para mejorar la seguridad en las implementaciones donde el acceso de usuarios externos está permitido. El director puede autenticar las solicitudes antes de enviarlas a los servidores internos. En caso de un ataque por denegación de servicio, el ataque termina en el director y no llega los servidores front-end.
  
### <a name="persistent-chat-server-roles"></a>Funciones de servidor de charla persistente

El chat persistente permite a los usuarios participar en conversaciones entre varias entidades sobre un tema en particular que persisten a lo largo del tiempo. El servidor front-end de chat persistente ejecuta el servicio de chat persistente, mientras que el servidor back-end de chat persistente almacena los datos del historial de chat y la información sobre categorías y salones de chat. El servidor back-end opcional de cumplimiento de chat persistente puede almacenar el contenido del chat y los eventos de cumplimiento con fines de cumplimiento.
  
Servidores que ejecutan Skype para Business Server Standard Edition también puede ejecutar charla persistente ubicados en el mismo servidor. No se puede colocar la persistente Chat servidor Front-End con el servidor Front-End de Enterprise Edition.
  
Para obtener más información, vea [Planear persistente Server Chat de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).
  
## <a name="high-availability-and-disaster-recovery-support"></a>Compatibilidad entre la alta disponibilidad y la recuperación ante desastres

Skype para Business Server proporciona una alta disponibilidad mediante redundancia de servidor a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.
  
Skype para Business Server también proporciona ante desastres recuperación medidas habilitando el emparejamiento de grupo. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.
  
Skype para Business Server también admite varias opciones de alta disponibilidad del servidor de extremo nuevo. Estos son los siguientes:
  
- Creación de reflejo de la base de datos
    
- Grupos de disponibilidad AlwaysOn
    
- Instancias de clúster de conmutación por error de AlwaysOn (FCI)
    
- Clústeres de conmutación por error de SQL
    
Para obtener detalles sobre el emparejamiento de grupo y atrás End Server alta disponibilidad, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
## <a name="server-collocation-in-skype-for-business-server-2015"></a>Colocación de servidores en Skype para Business Server 2015

Hemos usado el término colocar ya, pero ¿qué significa esto? Skype para Business Server 2015 permite localizar algunas características y funciones de servidor en el mismo servidor, que es la colocación, o en servidores diferentes, pero puede resultar confuso cuando usted comienza, y si está haciendo un Standard Edition o Enterprise Edition implementación de servidor (cada uno de ellos vienen con sus propias normas). Para ayudar con la planificación, incluimos colocación de servidores en implementaciones de servidores Standard Edition y Enterprise Edition Front-End pool (en la mayoría de los casos, esta información es idéntica y, cuando sea diferente, se llama específicamente).
  
### <a name="collocation-of-server-roles"></a>Combinación de roles del servidor

El servidor Standard Edition tiene las siguientes funciones ubicados (configuración adicional se requiere aunque), mientras se encuentra en el grupo de Front-End de Enterprise Edition, esta función puede ser ubicada, o implementar en un servidor independiente:
  
- Mediación
    
Estos roles del servidor se tienen que implementar en un servidor separado:
  
- Director
    
- Perimetral
    
- Servidor de interoperabilidad de vídeo
    
- Office Web Apps
    
### <a name="databases"></a>Bases de datos

En esta zona con diferencias reales entre implementaciones de servidores Standard Edition y en instalaciones de grupo de servidores Enterprise Edition, por lo que tendremos dos secciones siguientes, seguida de algunas reglas adicionales para ambos.
  
#### <a name="standard"></a>Standard

Dado que SQL Server Express está ubicado en el servidor Standard Edition y no se puede mover, esto es bastante sencillo. Además, si implementa el servidor de charla persistente en un servidor Standard Edition, usted también puede colocar la base de datos de cumplimiento de normas de Chat persistente en el servidor Standard Edition y el Chat persistente demasiado, pero no es necesario.
  
Éstos no pueden estar ubicados en el servidor Standard Edition, pero pueden ir en un servidor de base de datos única de sus propios:
  
- Base de datos de supervisión
    
- Base de datos de archivado
    
- Cualquier base de datos back-end para un grupo de servidores Enterprise Edition Front-End
    
#### <a name="enterprise"></a>Enterprise

Las siguientes bases de datos pueden ser colocadas en el mismo servidor de SQL Server:
  
- Base de datos back-end
    
- Base de datos de supervisión
    
- Base de datos de archivado
    
- Base de datos persistente de charla
    
- Base de datos de cumplimiento de normas de charla persistente
    
#### <a name="both"></a>Ambos

Ahora, hay algunas reglas adicionales a seguir para la colocación de Skype para bases de datos de Business Server 2015 en una sola instancia SQL, o en varias instancias SQL en la misma base de datos de SQL Server:
  
- Cada instancia SQL sólo puede contener una base de datos back-end único para un grupo de servidores Enterprise Edition Front-End, una sola base de datos de supervisión, una única base de datos de archivado, una única base de datos persistente de charla y una charla persistente cumplimiento base de datos.
    
- El servidor de base de datos no admite más de una agrupación de Front-End de Enterprise Edition, un servidor de archivado, un servidor que ejecuta la supervisión, una única base de datos persistente de charla y una charla persistente cumplimiento base de datos, pero puede admitir uno de cada uno, independientemente de si las bases de datos utilizan la misma instancia de SQL Server o instancias independientes de SQL Server.
    
### <a name="file-shares"></a>Recursos compartidos de archivos

El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:
  
- Servidor de base de datos, incluyendo el servidor de fondo detrás de un grupo de servidores Enterprise Edition Front-End
    
- Base de datos de supervisión
    
- Base de datos de archivado
    
- Base de datos persistente de charla
    
- Base de datos de cumplimiento de normas de charla persistente
    
> [!CAUTION]
> Tenga en cuenta que, si bien puede colocar el recurso compartido de archivos en estos servidores, es fundamental que tenga en cuenta que no lo recomendamos. Si ha colocado el recurso compartido de archivos con cualquier otro rol de servidor, asegúrese de que está supervisando el espacio en disco y los problemas de rendimiento de forma periódica. 
  
### <a name="keep-in-mind"></a>Recordatorio

- No se puede colocar un servidor proxy inverso, que no es un Skype para el componente servidor de negocios 2015 y no estén aún en la topología. Si desea permitir el uso compartido de contenido web para los usuarios federados, entre muchas otras cosas, tendrá a un proxy inverso. Si se necesita, siga adelante e implementar la compatibilidad con proxy inverso para Skype Business Server 2015 mediante la configuración de un servidor proxy inverso existente que ya está en la organización que está siendo utilizada por otras aplicaciones.
    
- No se puede colocar cualquier componente de mensajería unificada de Exchange o el componente de servidor de SharePoint con cualquier Skype para función de negocio servidor 2015.
    
## <a name="see-also"></a>Vea también

#### 

[Topologías de referencia para Skype para Business Server 2015](reference-topologies.md)

