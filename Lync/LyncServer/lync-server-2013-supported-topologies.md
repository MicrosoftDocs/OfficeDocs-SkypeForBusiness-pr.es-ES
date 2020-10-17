---
title: Topologías admitidas de Lync Server 2013
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
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523967"
---
# <a name="supported-topologies-in-lync-server-2013"></a>Topologías admitidas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-14_

Lync Server 2013 admite la implementación de sitios locales en una organización y la integración de implementaciones locales con las implementaciones de Lync Online, lo que se conoce como implementación híbrida. En una implementación híbrida, algunos usuarios se hospedan en la instalación local y algunos usuarios se hospedan en línea.

En el caso de las implementaciones locales, Lync Server 2013 admite la implementación de uno o varios sitios que se pueden escalar para satisfacer los requisitos de ubicación y disponibilidad elevados. Puede estructurar estos sitios y sus componentes para cumplir los requisitos de acceso y resistencia de su organización.

Una implementación local de Lync Server 2013 consta de lo siguiente:

  - La implementación debe incluir como mínimo un sitio central (también conocido como centro de datos). Cada sitio central debe tener como mínimo un grupo front-end Enterprise Edition o un servidor Standard Edition. Estos consisten en:
    
      - Un grupo de servidores front-end de Enterprise Edition, que está formado por uno o varios servidores front-end (normalmente, al menos dos servidores front-end por razones de escalabilidad) y un servidor back-end independiente. Un grupo de servidores front-end puede contener un máximo de doce servidores front-end. Se necesita un equilibrio de carga para varios servidores front-end. Para tráfico SIP, se recomienda un equilibrio de carga de DNS, aunque también se admite un equilibrio de carga de hardware. Si usa un equilibrio de carga de DNS para el tráfico SIP, seguirá necesitando un equilibrador de carga de hardware para el tráfico HTTP. Se recomienda crear un reflejo de SQL Server para obtener una alta disponibilidad de las bases de datos. La base de datos de back-end requiere una instancia independiente, aunque puede colocar en ella la base de datos de archivado, la base de datos de reflejo, la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente. Lync Server 2013 admite el uso de un clúster compartido para los recursos compartidos de archivos en la implementación. Para obtener más información sobre los requisitos de almacenamiento de bases de datos, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md). Para obtener más información sobre los requisitos de almacenamiento de archivos, consulte [compatibilidad de almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Si combinar las bases de datos de Lync Server, se recomienda encarecidamente evaluar todos los factores que pueden afectar a la disponibilidad y al rendimiento. Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.

        
        </div>
    
      - Un servidor Standard Edition, que incluye una base de datos colocada de SQL Server Express.

  - La implementación también puede tener uno o varios sitios de sucursales asociados al sitio central.

En esta sección se describen los sitios y los componentes de una implementación de Lync Server 2013. Para obtener más información sobre el sitio de Lync Server 2013, la topología y la planeación de componentes, consulte [Topology Basics debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) y las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación referente a la planeación. Para obtener más información sobre la integración de los componentes de versiones anteriores, vea [rutas de migración compatibles y escenarios de coexistencia en Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Los grupos de servidores extendidos no son compatibles con los roles de servidor de front-end, perimetral, mediación y director.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topología y componentes de un sitio central

Aunque una topología de sitio central debe incluir un grupo front-end o servidor Standard Edition, cada sitio central puede contener lo siguiente:

  - Varios grupos front-end, que pueden estar en el mismo dominio o en dominios diferentes. Sin embargo, todos los servidores front-end de un grupo front-end y el servidor back-end de dicho grupo deben encontrarse en el mismo dominio.

  - Varios servidores Standard Edition.

  - Office Web Apps Server, que se usa con aplicaciones Web de Office en Lync Server 2013 para controlar el uso compartido y la representación de presentaciones de Microsoft PowerPoint.

  - Servidor perimetral o grupo de servidores perimetrales en la red perimetral, si desea que la implementación admita socios federados, conectividad de mensajería instantánea pública, una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP), acceso de usuarios remotos, participación de usuarios anónimos en reuniones o mensajería unificada (MU) de Exchange. No se puede colocar ningún otro rol de servidor en un servidor perimetral. Se recomienda un equilibrio de carga de DNS, siempre que sea apropiado, aunque también se admite un equilibrio de carga de hardware. La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz perimetral y el equilibrio de carga de hardware en la otra interfaz perimetral. Para obtener más información sobre los requisitos y la compatibilidad de equilibrio de carga, consulte [Planning for external User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación de planeación y [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.

  - Servidor o grupo de servidores de mediación, si desea admitir Enterprise Voice o conferencias de acceso telefónico local en un grupo de servidores front-end en el sitio central. En función de cómo implemente la asistencia de telefonía IP empresarial, puede combinar el servidor de mediación en un grupo de servidores front-end (opción predeterminada) o implementar un servidor o grupo de servidores de mediación independiente. Puede usar el equilibrio de carga de DNS, hardware o aplicación (cuando corresponda) para distribuir el tráfico de la puerta de enlace del grupo de servidores de mediación, incluidos una puerta de enlace RTC, una IP-PBX o un control de borde de sesión (SBC) del tronco SIP. Para obtener más información sobre cómo planear la topología del servidor de mediación adecuada, consulte [directrices de implementación para servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) en la documentación referente a la planeación.

  - Servidor de chat persistente, si desea que los usuarios puedan participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo. Para proporcionar más capacidad y aumentar la confiabilidad, la topología puede incluir varios equipos que ejecuten el servidor de chat persistente. No puede combinar servidor de chat persistente con otros roles de servidor en un grupo de servidores Enterprise. Sin embargo, puede combinar servidor de chat persistente en un servidor Standard Edition. El chat persistente requiere una base de datos y, si implementa el cumplimiento de chat persistente, también necesitará una base de datos de cumplimiento de chat persistente; sin embargo, las bases de datos pueden colocarse con la base de datos de archivado, la base de datos de supervisión o en el servidor back-en de un grupo de servidores front-end Enterprise Edition. Para obtener más información sobre cómo planear la topología adecuada del servidor de chat persistente, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.

  - Servidor de supervisión, si desea permitir en su implementación la recopilación de datos de la calidad de la experiencia (QoE) de audio y vídeo y el registro de detalles de las llamadas (CDR) para Enterprise Voice y conferencias A/V. Opcionalmente, puede instalar Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa datos de supervisión de CDR y QoE para generar alertas cercanas al tiempo real que muestren el estado de la confiabilidad de las llamadas y la calidad de los medios. El servidor de supervisión, cuando se implementa, se coloca en los servidores front-end o en el servidor Standard Edition. El servidor de supervisión requiere una base de datos, pero la base de datos se puede colocar en la base de datos de archivado, la base de datos de chat persistente, la base de datos de cumplimiento de chat persistente o en el servidor back-end de un grupo de servidores front-end Enterprise Edition.

  - Servidor de archivado, si desea archivar el contenido de las comunicaciones y las reuniones de mensajería instantánea (por razones de cumplimiento de normas) en su implementación. El servidor de archivado, cuando se implementa se coloca en servidores front-end o en un servidor Standard Edition. El almacenamiento de archivado requiere la implementación de una base de datos de archivado o la integración con el almacenamiento de Exchange 2013. Si usa ambos, lo que se conoce como *modo mixto*, el almacenamiento de Exchange 2013 se usa para almacenar datos de archivo para los usuarios que están hospedados en Exchange 2013 y la base de datos de archivado se usa para archivar datos para todos los demás usuarios de la implementación. Si requiere una base de datos de archivo, esta base de datos se puede colocar en la base de datos de supervisión, en la base de datos de chat persistente, en la base de datos de cumplimiento de chat persistente o en el servidor back-end de un grupo de servidores front-end. Para obtener más información sobre cómo planear la topología de archivado adecuada, consulte [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación.

  - Un director o un grupo de directores, si desea facilitar la resistencia y el redireccionamiento de las solicitudes de usuario de Lync Server 2013 al grupo principal del usuario, que puede ser un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Recomendamos implementar un director o grupo de directores en cada sitio central que permita el acceso de usuarios externos y en cada sitio central en el que implemente uno o varios grupos front-end. Cada grupo de directores puede tener un máximo de diez directores. Un director no se puede instalar con ningún otro rol de servidor. Para obtener más información sobre cómo planear la topología de Director adecuada, consulte [escenarios para el Director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación referente a la planeación.

  - Proxy inverso, que no es un componente 2013 de Lync Server, pero es necesario si desea admitir el uso compartido de contenido web para usuarios federados o para admitir el tráfico de movilidad. No se puede combinar un servidor proxy inverso con ningún rol de servidor de Lync Server 2013, pero se puede implementar la compatibilidad con un proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente en la organización que se usa para otras aplicaciones. Para obtener más información sobre los servidores proxy inversos, consulte [configuración de servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) en la documentación sobre implementación.

<div>


> [!NOTE]  
> En Lync Server 2013, la Conferencia, la supervisión y el archivado de A/V se ejecutan en servidores front-end y ya no son roles de servidor independientes.



</div>

Todos los grupos front-end y servidores Standard Edition que implemente en un sitio central comparten cualquiera de los siguientes servidores que implemente para el sitio central:

  - Director o grupo de directores

  - Servidor de mediación independiente o grupo

  - Servidor Office Web Apps

  - Servidor perimetral o grupo perimetral

  - Grupo o servidor de chat persistente

  - Supervisión

  - Archivado

<div>


> [!NOTE]  
> Se puede implementar un servidor de mensajería unificada de Exchange con la implementación de Lync Server 2013 si desea admitir la integración de la mensajería unificada de Exchange 2013, pero no es un componente del sitio de Lync Server 2013.



</div>

Varios sitios centrales también pueden compartir cualquiera de los siguientes servidores que implemente en un sitio central:

  - Servidor de mediación independiente o grupo

  - Servidor perimetral o grupo perimetral

  - Grupo o servidor de chat persistente

  - Archivado

  - Supervisión

<div>


> [!NOTE]  
> Un servidor de mensajería unificada de Exchange puede implementarse con la implementación de Lync Server 2013 y compartirse con varios sitios centrales, pero no es un componente del sitio de Lync Server 2013.



</div>

Para obtener más información sobre las funciones y funciones del servidor de Lync Server 2013, consulte [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md) en la documentación referente a la planeación.

Para obtener un resumen de la compatibilidad del servidor de Lync Server 2013 Server combinación, consulte Supported [Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md).

Además de las funciones y funciones de servidor descritas anteriormente en esta sección, Lync Server 2013 tiene componentes y opciones adicionales, que pueden incluir algunas o todas las opciones siguientes:

  - Firewalls

  - Puertas de enlace RTC (si implementa Enterprise Voice)

  - Servidor de mensajería unificada de Exchange

  - Equilibrio de carga de DNS

  - Equilibradores de carga de hardware

  - Bases de datos SQL Server

  - Recursos compartidos de archivos

Para obtener más información sobre las características, los componentes y las opciones de Lync Server 2013, consulte la documentación de planeación.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topología y componentes de sitios de sucursales

Un sitio de sucursal está asociado a un sitio central, y todas las aplicaciones de sucursal con funciones de supervivencia de un sitio de sucursal están asociadas con un grupo de front-end Enterprise Edition o con un servidor Standard Edition del sitio central asociado. Los sitios de sucursales dependen del sitio central para la mayoría de sus funciones, por lo que entre los componentes de un sitio de sucursal solo pueden estar los siguientes:

  - Una aplicación de sucursal con funciones de supervivencia que combina una puerta de enlace de red telefónica conmutada (RTC) con alguna funcionalidad de Lync Server. Un servidor de mediación se puede combinar con la instancia del registrador en la aplicación de sucursal con funciones de supervivencia y se puede implementar un servidor de mediación independiente o un grupo de servidores de mediación.

  - Un servidor de sucursal con funciones de supervivencia, que es un servidor que ejecuta Windows Server con el registrador de Lync Server 2013 registrador y el software del servidor de mediación instalado.

  - Una puerta de enlace RTC independiente (no forma parte de la aplicación de sucursal con funciones de supervivencia) y un servidor de mediación independiente.

Los requisitos de los servidores de sucursal con funciones de supervivencia son los mismos que los de cualquier rol de servidor de Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

