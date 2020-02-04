---
title: 'Lync Server 2013: Topologías compatibles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologías compatibles en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-14_

Lync Server 2013 admite la implementación de sitios locales en una organización y la integración de implementaciones locales con implementaciones de Lync Online, que se conoce como una implementación híbrida. En una implementación híbrida, algunos usuarios están alojados en locales y algunos usuarios están alojados en línea.

En el caso de implementaciones locales, Lync Server 2013 admite la implementación de uno o varios sitios que se pueden escalar para cumplir con los requisitos de ubicación y disponibilidad elevados. Puede estructurar estos sitios y sus componentes para cumplir con los requisitos de acceso y resistencia de su organización.

Una implementación local de Lync Server 2013 consta de lo siguiente:

  - Su implementación debe incluir al menos un sitio central (también conocido como un centro de datos). Cada sitio central debe contener al menos un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Se componen de las siguientes acciones:
    
      - El grupo de servidores front-end Enterprise Edition, que consta de uno o varios servidores front-end (por lo general, al menos dos servidores front-end para escalabilidad) y un servidor back-end independiente. Un grupo de servidores front-end puede contener un máximo de doce servidores front-end. El equilibrio de carga es necesario para varios servidores front-end. Para el tráfico SIP, recomendamos el equilibrio de carga de DNS, pero también se admite el equilibrio de carga de hardware. Si usa el equilibrio de carga de DNS para el tráfico SIP, aún necesita un equilibrador de carga de hardware para el tráfico HTTP. Recomendamos el reflejo de SQL Server para una alta disponibilidad de las bases de datos. La base de datos back-end requiere una instancia independiente, pero puede Collocate la base de datos de archivado, la supervisión de la base de datos, la base de datos de chat persistente y la base de datos de cumplimiento persistente de la conversación. Lync Server 2013 admite el uso de un clúster compartido para los archivos compartidos en la implementación. Para obtener más información sobre los requisitos de almacenamiento de base de datos, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md). Para obtener más información sobre los requisitos de almacenamiento de archivos, consulte [compatibilidad de almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Si Collocate bases de datos de Lync Server, se recomienda encarecidamente evaluar todos los factores que pueden afectar a la disponibilidad y el rendimiento. Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.

        
        </div>
    
      - Servidor Standard Edition, que incluye una base de datos de SQL Server Express.

  - Su implementación también puede tener uno o más sitios de sucursales asociados con un sitio central.

En esta sección se describen los sitios y componentes de una implementación de Lync Server 2013. Para obtener más información sobre el sitio de Lync Server 2013, la topología y la planeación de componentes, consulte fundamentos de la [topología que debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) y las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación de planificación. Para obtener más información sobre la integración de componentes de versiones anteriores, consulte [rutas de migración compatibles y escenarios de coexistencia en Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Los grupos de servidores estirados no son compatibles con los roles de servidor de front-end, Edge, mediación y director.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologías y componentes de sitio central (local)

Aunque una topología de sitio central debe incluir un grupo de servidores front-end o un servidor Standard Edition, cada sitio central también puede contener lo siguiente:

  - Varias agrupaciones front end, que pueden estar en el mismo dominio o en dominios diferentes. Sin embargo, todos los servidores front-end de un grupo de servidores front-end y el servidor back-end de ese grupo deben estar en el mismo dominio.

  - Varios servidores Standard Edition.

  - Office Web Apps Server, que se usa con aplicaciones Web de Office en Lync Server 2013, para controlar el uso compartido y el procesamiento de presentaciones de Microsoft PowerPoint.

  - Servidor perimetral o grupo Edge en la red perimetral, si desea que su implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP), acceso de usuarios remotos, participación de usuarios anónimos en reuniones, o mensajería unificada de Exchange (UM). No puede Collocate ningún otro rol de servidor con un servidor perimetral. Recomendamos el equilibrio de carga de DNS, cuando corresponda, pero también se admite el equilibrio de carga de hardware. La interfaz perimetral interna y la interfaz perimetral externa necesitan usar el mismo tipo de equilibrio de carga. No puede usar equilibrio de carga de DNS en una interfaz perimetral y equilibrio de carga de hardware en la otra interfaz perimetral. Para obtener más información sobre los requisitos de equilibrio de carga y la compatibilidad, consulte [planear el acceso de usuarios externos en Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación e [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.

  - Servidor o grupo de mediación, si desea proporcionar soporte técnico de telefonía IP empresarial o conferencias de acceso telefónico local en un grupo de servidores front-end en el sitio central. Según el modo en que implemente la asistencia de voz empresarial, puede Collocate el servidor de mediación en un grupo de servidores front-end (el valor predeterminado) o implementar un servidor o grupo de mediación independiente. Puede usar DNS, hardware o el equilibrio de carga de la aplicación (cuando corresponda) para distribuir el tráfico de un grupo de puerta de enlace del grupo de servidores de mediación, como una puerta de enlace RTC, IP-PBX o un control de borde de sesión (SBC) de SIP. Para obtener más información sobre cómo planear la topología de servidor de mediación adecuada, consulte [directrices de implementación para servidor de mediación en Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) en la documentación de planeación.

  - Servidor de chat persistente, si desea que los usuarios puedan participar a lo largo del tiempo en conversaciones basadas en temas y en varias partes. Para proporcionar más capacidad y una mayor confiabilidad, su topología puede incluir varios equipos que ejecuten el servidor de chat persistente. No puede Collocate servidor de chat persistente con otros roles de servidor en un grupo de servidores Enterprise. Sin embargo, puede Collocate el servidor de chat persistente en un servidor Standard Edition. El chat persistente requiere una base de datos y, si implementa un cumplimiento persistente de las conversaciones, una base de datos de cumplimiento persistente de la conversación, pero las bases de datos se pueden colocar con la base de datos de archivado, la base de datos de supervisión o el servidor back-end de una edición Enterprise Grupo de servidores front-end. Para obtener más información sobre cómo planear la topología adecuada del servidor de chat persistente, consulte [planificación de servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planificación.

  - Supervisión: Si desea admitir la recopilación de datos de la calidad de la experiencia de audio/vídeo (QoE) y la grabación de detalles de llamadas (CDR) de las conferencias de telefonía IP empresarial y A/V de su implementación. De manera opcional, puede instalar Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa la supervisión de datos de CDR y QoE para generar alertas casi en tiempo real que muestran el estado de la confiabilidad de las llamadas y la calidad de los medios. La supervisión, cuando se implementa, se encuentra en servidores de aplicaciones para el usuario o en un servidor Standard Edition. La supervisión requiere una base de datos, pero la base de datos puede colocarse con la base de datos de archivado, la base de datos de chat persistente, la base de datos de cumplimiento persistente de chat o en el servidor back-end de un grupo de servidores front end Enterprise Edition.

  - Archivar, si desea archivar las comunicaciones y el contenido de la reunión de mensajería instantánea (por razones de cumplimiento normativo) en su implementación. El archivado, cuando se implementa, se encuentra en servidores front-end o en un servidor Standard Edition. El almacenamiento de archivado requiere la implementación de una base de datos de archivado o la integración con el almacenamiento de Exchange 2013. Si usa ambos, lo que se conoce como *modo mixto*, el almacenamiento de Exchange 2013 se usa para almacenar datos de archivo para los usuarios que se encuentran en el 2013 de Exchange y la base de datos de archivado se usa para archivar los datos de todos los demás usuarios de la implementación. Si necesita una base de datos de archivado, la base de datos puede colocarse en la base de datos de supervisión, en la base de datos de chat persistente, en una base de datos de cumplimiento persistente o en el servidor back-end de un grupo de servidores front-end. Para obtener detalles sobre el planeamiento de la topología de archivado adecuada, consulte [planear el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.

  - Grupo de directores o directores, si desea facilitar la resistencia y el redireccionamiento de las solicitudes de usuario de Lync Server 2013 al grupo de hogar del usuario, que puede ser un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Le recomendamos que implemente un director o un grupo de directores en cada sitio central que admita el acceso de usuarios externos y en cada sitio central en el que implemente uno o más grupos front-end. Cada grupo de directores puede contener un máximo de diez directores. No se puede incluir un director con ningún otro rol de servidor. Para obtener más información sobre cómo planear la topología de Director adecuada, consulte [escenarios del Director de Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación de planeación.

  - Proxy inverso, que no es un componente de 2013 de Lync Server, pero es necesario si desea permitir el uso compartido de contenido web para usuarios federados o para admitir el tráfico de movilidad. No se puede Collocate un servidor proxy inverso con ningún rol de servidor de Lync Server 2013, pero puede implementar compatibilidad con proxy invertida para una implementación de Lync Server 2013 si configura la compatibilidad en un servidor proxy inverso existente de su organización que se usa para otros aplicación. Para obtener detalles sobre los servidores proxy inversos, vea [configuración de servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) en la documentación de implementación.

<div>


> [!NOTE]  
> En Lync Server 2013, las conferencias, la supervisión y el archivado de A/V se ejecutan en servidores de aplicaciones para el usuario y ya no tienen roles de servidor diferentes.



</div>

Todas las agrupaciones de front-end y los servidores Standard Edition que se implementan en un sitio central comparten cualquiera de las siguientes opciones de implementación para el sitio central:

  - Grupo de directores o directores

  - Servidor o grupo de mediación independiente

  - Servidor Office Web Apps

  - Servidor perimetral o grupo Edge

  - Servidor o grupo de servidores de chat persistentes

  - Supervisión

  - Archivado

<div>


> [!NOTE]  
> Es posible implementar un servidor de mensajería unificada de Exchange con la implementación de Lync Server 2013 si desea admitir la integración de la mensajería unificada de Exchange 2013, pero no es un componente del sitio de Lync Server 2013.



</div>

Varios sitios centrales también pueden compartir cualquiera de las siguientes opciones que se implementan en un sitio central:

  - Servidor o grupo de mediación independiente

  - Servidor perimetral o grupo Edge

  - Servidor o grupo de servidores de chat persistentes

  - Archivado

  - Supervisión

<div>


> [!NOTE]  
> Es posible implementar un servidor de mensajería unificada de Exchange con la implementación de Lync Server 2013 y compartirlo con varios sitios centrales, pero no es un componente del sitio de Lync Server 2013.



</div>

Para obtener más información sobre los roles y la funcionalidad del servidor de Lync Server 2013, vea [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md) en la documentación de planeación.

Para obtener un resumen de la compatibilidad de servidor de Lync Server 2013 Server collocation, consulte compatibilidad con [servidores de collocation de Lync server 2013](lync-server-2013-supported-server-collocation.md).

Además de los roles de servidor y la funcionalidad que se han explicado anteriormente en esta sección, Lync Server 2013 tiene componentes y opciones adicionales, que pueden incluir algunos o todos los elementos siguientes:

  - Firewalls

  - Puertas de enlace RTC (si se implementa la telefonía IP empresarial)

  - Servidor de mensajería unificada de Exchange

  - Equilibrio de carga de DNS

  - Equilibradores de carga de hardware

  - Bases de datos de SQL Server

  - Recursos compartidos de archivos

Para obtener detalles sobre todas las características, componentes y opciones de Lync Server 2013, consulte la documentación de planeación.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologías y componentes de sitio de sucursal (local)

Un sitio de sucursal está asociado con un sitio central, y cada uno de los dispositivos de sucursal con la supervivencia de un sitio de sucursal está asociado con un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition en el sitio central asociado. Los sitios de sucursales dependen del sitio central para la mayor parte de su funcionalidad, de modo que los componentes de un sitio de sucursal contienen solo lo siguiente:

  - Un equipo de sucursales con la que se combina una puerta de enlace de red telefónica conmutada (RTC) con alguna funcionalidad de Lync Server. Se puede dar un servidor de mediación con la instancia del registrador de la aplicación de rama superviviente y puede implementar un servidor de mediación o un grupo de servidores de mediación independientes.

  - Un servidor de sucursal con la supervivencia, que es un servidor de Windows Server con el registrador de Lync Server 2013 y el software de servidor de mediación instalado.

  - Una puerta de enlace independiente de RTC (que no forma parte del equipo de sucursal con supervivencia) y un servidor de mediación independiente.

Los requisitos para servidores de sucursal revivientes son los mismos que los de cualquier rol de servidor de Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

