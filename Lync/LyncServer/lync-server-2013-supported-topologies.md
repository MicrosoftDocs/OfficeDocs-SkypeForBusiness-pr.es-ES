---
title: 'Lync Server 2013: Topologías compatibles'
TOCTitle: Topologías compatibles
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48274888
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologías compatibles en Lync Server 2013

 

_**Última modificación del tema:** 2014-01-14_

El Lync Server 2013 es compatible con la implementación de sitios locales en una organización y la integración de implementaciones locales con las implementaciones Skype Empresarial Online, que se conoce como una implementación híbrida. En una implementación híbrida, algunos usuarios se hospedan en la instalación local y algunos usuarios se hospedan en línea.

Para las implementaciones locales, el Lync Server 2013 admite implementaciones de uno o varios sitios que se pueden escalar para satisfacer requisitos de alta disponibilidad y ubicación. Puede estructurar estos sitios y sus componentes para cumplir los requisitos de acceso y resistencia de su organización.

Una implementación local Lync Server 2013 consiste en lo siguiente:

  - La implementación debe incluir como mínimo un sitio central (también conocido como centro de datos). Cada sitio central debe tener como mínimo un grupo front-end Enterprise Edition o un servidor Standard Edition. Estos consisten en:
    
      - Un grupo de servidores front-end de Enterprise Edition, que está formado por uno o varios servidores front-end (normalmente, al menos dos servidores front-end por razones de escalabilidad) y un servidor back-end independiente. Un grupo front-end puede tener un máximo de doce servidores front-end. Se necesita un equilibrio de carga para varios servidores front-end. Para tráfico SIP, se recomienda un equilibrio de carga de DNS, aunque también se admite un equilibrio de carga de hardware. Si usa un equilibrio de carga de DNS para el tráfico SIP, seguirá necesitando un equilibrador de carga de hardware para el tráfico HTTP. Se recomienda SQL Server para la creación de reflejos de bases de datos. La base de datos de back-end requiere una instancia independiente, aunque puede colocar en ella la base de datos de archivado, la base de datos de supervisión, la base de datos de chat persistente y la base de datos de cumplimiento de chat persistente. Lync Server 2013 admite el uso de un clúster compartido para el uso compartido de archivos en su implementación. Para obtener más información sobre los requisitos de almacenamiento de base de datos, vea [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md). Para obtener más información acerca de los requisitos de almacenamiento de archivos, consulte [Compatibilidad con el almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        > [!IMPORTANT]  
        > Si combina bases de datos de Lync Server con otras bases de datos, le recomendamos encarecidamente que evalúe todos los factores que pueden afectar a la disponibilidad y al rendimiento. Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.
        
    
      - Un servidor Standard Edition, que incluye una base de datos colocada de SQL Server Express.

  - La implementación también puede tener uno o varios sitios de sucursales asociados al sitio central.

En esta sección se describen los sitios y componentes de una implementación de Lync Server 2013. Para obtener información detallada acerca del sitio, la topología y la planeación de componentes de Lync Server 2013 consulte [Aspectos básicos de la topología a tener en cuenta antes de la planificación para Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) y [Topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md) en la documentación referente a la planeación. Para obtener información detallada acerca de la integración de componentes anteriores, consulte [Rutas de acceso de migración compatibles y escenarios de coexistencia en Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).


> [!NOTE]
> Los grupos de servidores extendidos no son compatibles con los roles de servidor front-end, perimetral, de mediación y de director.



## Topología y componentes de un sitio central

Aunque una topología de sitio central debe incluir un grupo front-end o servidor Standard Edition, cada sitio central puede contener lo siguiente:

  - Varios grupos front-end, que pueden estar en el mismo dominio o en dominios diferentes. Sin embargo, todos los servidores front-end de un grupo front-end y el servidor back-end de dicho grupo deben encontrarse en el mismo dominio.

  - Varios servidores Standard Edition.

  - El Servidor Office Web Apps, que se utiliza con aplicaciones web de Office en Lync Server 2013 para controlar el uso compartido y la representación de las presentaciones de Microsoft PowerPoint.

  - Un servidor o grupo perimetral de la red perimetral, si desea que su implementación admita socios federados, conectividad de mensajería instantánea pública, puerta de enlace de protocolo extensible de mensajería y presencia (XMPP), acceso de usuarios remotos, participación de usuarios anónimos en reuniones o Mensajería unificada de Exchange (UM). No se puede colocar ningún otro rol de servidor en un servidor perimetral. Se recomienda un equilibrio de carga de DNS, siempre que sea apropiado, aunque también se admite un equilibrio de carga de hardware. La interfaz perimetral interna y la interfaz perimetral externa deben usar el mismo tipo de equilibrio de carga. No puede usar el equilibrio de carga de DNS en una interfaz perimetral y el equilibro de carga de hardware en la otra interfaz perimetral. Para obtener información detallada acerca de los requisitos y la compatibilidad del equilibrio de carga, consulte [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) en la documentación sobre planeación y [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.

  - Servidor o grupo de mediación, si desea permitir Enterprise Voice o conferencias de acceso telefónico en un grupo front-end en el sitio central. En función del modo en el que implemente la compatibilidad con Enterprise Voice, puede colocar el servidor de mediación en un grupo front-end (el predeterminado) o implementar un servidor o grupo de mediación independiente. Puede usar equilibrio de carga de DNS, hardware o aplicaciones (según corresponda) para distribuir el tráfico desde una puerta de enlace del mismo nivel del grupo de servidores de mediación, incluida una puerta de enlace RTC, un sistema IP-PBX o un control de borde de sesión (SBC) troncal SIP. Para obtener información detallada acerca de la topología de servidor de mediación adecuada, consulte [Directrices de implementación para el servidor de mediación en Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) en la documentación referente a la planeación.

  - Servidor de chat persistente, si desea que los usuarios puedan participar en conversaciones entre varias personas basadas en el tema que persisten a lo largo del tiempo. Para ofrecer más capacidad y una mayor fiabilidad, su topología puede incluir equipos que ejecuten el Servidor de chat persistente. No puede colocar un Servidor de chat persistente con otros roles de servidores en un grupo de Enterprise. Sin embargo, puede colocar un Servidor de chat persistente en un servidor Standard Edition. El chat persistente requiere una base de datos y, si implementa el cumplimiento de chat persistente, también necesitará una base de datos de cumplimiento de chat persistente; sin embargo, las bases de datos pueden colocarse con la base de datos de archivado, la base de datos de supervisión o en el servidor back-en de un grupo de servidores front-end Enterprise Edition. Para obtener información detallada acerca de la topología de Servidor de chat persistente adecuada, consulte [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.

  - Servidor de supervisión, si desea permitir en su implementación la recopilación de datos de la calidad de la experiencia (QoE) de audio y vídeo y el registro de detalles de las llamadas (CDR) para Enterprise Voice y conferencias A/V. Si lo desea, también puede instalar el Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que usa la supervisión de CDR y los datos de QoE para generar, prácticamente en tiempo real, alertas que muestran el estado de la fiabilidad de las llamadas y la calidad de los medios. El servidor de supervisión, cuando se implementa, se coloca en los servidores front-end o en el servidor Standard Edition. El servidor de supervisión requiere una base de datos, pero la base de datos se puede colocar en la base de datos de archivado, la base de datos de chat persistente, la base de datos de cumplimiento de chat persistente o en el servidor back-end de un grupo de servidores front-end Enterprise Edition.

  - Servidor de archivado, si desea archivar el contenido de las comunicaciones y las reuniones de mensajería instantánea (por razones de cumplimiento de normas) en su implementación. El servidor de archivado, cuando se implementa se coloca en servidores front-end o en un servidor Standard Edition. Su almacenamiento requiere la implementación de una base de datos de archivado o la integración con el almacenamiento de Exchange 2013. Si usa los dos, lo que se conoce como un *modo mixto* , el almacenamiento de Exchange 2013 se utiliza para almacenar datos de archivo para los usuarios que se hospedan en Exchange 2013, y la base de datos de archivo se utiliza para todos los demás usuarios en su implementación. Si requiere una base de datos de archivo, esta base de datos se puede colocar en la base de datos de supervisión, en la base de datos de chat persistente, en la base de datos de cumplimiento de chat persistente o en el servidor back-end de un grupo de servidores front-end. Para obtener información detallada acerca de la topología de archivo adecuada, consulte [Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación referente a la planeación.

  - Director o grupo de directores, si desea facilitar la resistencia y redireccionamiento de solicitudes de usuario de Lync Server 2013 al grupo principal del usuario, que puede ser un grupo front-end Enterprise Edition o un servidor Standard Edition. Recomendamos implementar un director o grupo de directores en cada sitio central que permita el acceso de usuarios externos y en cada sitio central en el que implemente uno o varios grupos front-end. Cada grupo de directores puede tener un máximo de diez directores. Un director no se puede instalar con ningún otro rol de servidor. Para obtener información detallada acerca de la topología de director adecuada, consulte [Escenarios para el director en Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) en la documentación referente a la planeación.

  - Servidor proxy inverso, que no es componente de Lync Server 2013 pero es necesario si desea permitir el uso compartido de contenidos web para los usuarios federados o para el tráfico de movilidad. No puede combinar un servidor proxy inverso con ningún rol de servidor de Lync Server 2013, aunque sí puede dar compatibilidad con servidores proxy inversos para una implementación de Lync Server 2013 configurando la compatibilidad en un servidor proxy inverso existente en su organización que se utilice para otras aplicaciones. Para obtener más detalles acerca de los servidores proxy inversos, consulte [Configuración de los servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) en la documentación referente a la implementación.


> [!NOTE]
> En Lync Server 2013, las conferencias A/V, la supervisión y el archivado ejecutados en servidores front-end han dejado de ser roles de servidor separados.



Todos los grupos front-end y servidores Standard Edition que implemente en un sitio central comparten cualquiera de los siguientes servidores que implemente para el sitio central:

  - Director o grupo de directores

  - Servidor de mediación independiente o grupo

  - Servidor Office Web Apps

  - Servidor perimetral o grupo perimetral

  - Grupo o servidor de chat persistente

  - Supervisión

  - Archivado


> [!NOTE]
> Puede implementar un servidor Mensajería unificada de Exchange con la implementación de Lync Server 2013 si desea admitir la integración de mensajería unificada de Exchange 2013, aunque este no sea un componente del sitio de Lync Server 2013.



Varios sitios centrales también pueden compartir cualquiera de los siguientes servidores que implemente en un sitio central:

  - Servidor de mediación independiente o grupo

  - Servidor perimetral o grupo perimetral

  - Grupo o servidor de chat persistente

  - Archivado

  - Supervisión


> [!NOTE]
> Es posible implementar un servidor Mensajería unificada de Exchange con la implementación de Lync Server 2013 y compartirlo entre varios sitios centrales, aunque este no sea un componente del sitio Lync Server 2013.



Para obtener información detallada acerca de los roles de servidor de Lync Server 2013, consulte [Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md) en la documentación sobre la planeación.

Para ver un resumen de los roles de servidor de Lync Server 2013 que se pueden colocar con otros roles de servidor, consulte [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md).

Además de los roles y la funcionalidad de servidor explicados en la sección anterior, Lync Server 2013 dispone de componentes y opciones adicionales que pueden incluir alguno de los siguientes elementos o todos ellos:

  - Firewalls

  - Puertas de enlace RTC (si implementa Enterprise Voice)

  - Servidor Mensajería unificada de Exchange

  - Equilibrio de carga de DNS

  - Equilibradores de carga de hardware

  - Bases de datos SQL Server

  - Recursos compartidos de archivos

Para obtener información detallada acerca de todas las funciones, componentes y opciones de Lync Server 2013 consulte la documentación sobre la planeación.

## Topología y componentes de sitios de sucursales

Un sitio de sucursal está asociado a un sitio central, y todas las aplicaciones de sucursal con funciones de supervivencia de un sitio de sucursal están asociadas con un grupo de front-end Enterprise Edition o con un servidor Standard Edition del sitio central asociado. Los sitios de sucursales dependen del sitio central para la mayoría de sus funciones, por lo que entre los componentes de un sitio de sucursal solo pueden estar los siguientes:

  - Un Aplicación de sucursal con funciones de supervivencia, que combina una puerta de enlace de una red telefónica conmutada (RTC) con algunas funciones de Lync Server. Puede colocar un servidor de mediación con la instancia del registrador de Aplicación de sucursal con funciones de supervivencia e implementar un servidor de mediación independiente o un grupo de servidores de mediación.

  - Un servidor de sucursal con funciones de supervivencia, que es un servidor de Windows Server que tiene instalado un software de servidor de registrador y de mediación de Lync Server 2013.

  - Una puerta de enlace RTC independiente (no forma parte de la aplicación de sucursal con funciones de supervivencia) y un servidor de mediación independiente.

Los requisitos para servidores de sucursal con funciones de supervivencia son los mismos que para cualquier rol de servidor de Lync Server 2013.

