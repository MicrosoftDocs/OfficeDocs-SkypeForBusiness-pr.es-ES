---
title: "Topología de referencia para grandes organizaciones con varios centros de datos"
TOCTitle: Topología de referencia para grandes organizaciones con varios centros de datos
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48276126
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topología de referencia para grandes organizaciones con varios centros de datos para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-22_

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el Sitio central A, 20 000 en el Sitio central B y un total de 10 000 en el Sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con un número cualquiera de usuarios.

Además de la alta disponibilidad de los grupos de servidores de Servidores front-end, esta topología es compatible con recuperación ante desastres. Los Grupos de servidores front-end en los sitios centrales A y B quedarán emparejados. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá pasar los servicios para los usuarios afectados al grupo emparejado en el sitio no afectado.

Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.

**Información general de la topología de referencia para organizaciones de gran tamaño con varios centros de datos**

![Topología de referencia para varios centros de datos](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topología de referencia para varios centros de datos")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central A**

![Topologías de referencia de planeación A](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "Topologías de referencia de planeación A")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central B**

![Topologías de referencia de planeación B](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "Topologías de referencia de planeación B")

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central C**

![Topologías de referencia de planeación C](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "Topologías de referencia de planeación C")

  - **Grupos de servidores front-end se emparejan para habilitar la recuperación ante desastres.**   Los Grupos de servidores front-end del Sitio A y el Sitio B se emparejan entre sí para ofrecer compatibilidad con recuperación ante desastres. Si el grupo de servidores de un sitio causa un error, el administrador puede activar la conmutación por error y pasar lo usuarios de ese sitio al Grupo de servidores front-end emparejado del otro sitio con un mínimo de interrupción del servicio para los usuarios. Cada uno de estos dos grupos de servidores front-end tiene seis servidores, suficiente para 40 000 usuarios en ambos grupos en caso de conmutación por error. Para obtener más información, consulte [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Servidores back-end se reflejan**   Para ofrecer mayor disponibilidad de cara a las características básicas, la organización ha implementado un par reflejado de Servidores back-end para cada Grupo de servidores front-end. Se trata de una topología opcional y puede optar por implementar un único Servidor back-end en su lugar.

  - **Uso del servidor Standard Edition en un sitio de sucursal.** Esta organización considera el Sitio C como un sitio de sucursal porque solo tiene 600 empleados. Sin embargo, los usuarios de este sitio realizan muchas conferencias de A/V entre ellos. Si se hubiera implementado en Lync Server como sitio de sucursal, los medios de dichas conferencias se ejecutarían en la red de área extensa (WAN) hasta y desde un sitio central que tuviera un front-end implementado. Para evitar esta posible carga de ancho de banda, se han instalado un par de servidores Standard Edition en este sitio, que hospedarán las conferencias. Y como se han instalado allí los servidores Standard Edition, Lync Server lo considera por definición un sitio central y lo trata como tal en Generador de topologías y en la Herramienta de planeación.
    
    Aquí un solo servidor Standard Edition puede ofrecer suficiente rendimiento, pero la organización ha implementado dos y los ha emparejado para ofrecer alta disponibilidad en caso de que un servidor deje de funcionar.
    
    A pesar de que el Sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el Sitio C usará los servidores perimetrales implementados en el Sitio A.

  - **Supervisión y Archivado**   Esta organización ha implementado Supervisión y Archivado. Si se implementa Supervisión o Archivado, se ejecutará en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el Sitio central B. Las bases de datos de esta ubicación reciben datos de Supervisión y Archivado desde los servidores front-end de todos los sitios.

  - **Opciones de implementación en sitios de sucursal.**   Esta organización tiene en realidad más de 50 sitios de sucursal y en los diagramas detallados solo se muestran tres de ellos. Los Sitios de sucursal 1 y 3 no disponen de un vínculo WAN resistente al sitio central, por lo que tienen implementadas Aplicaciones de sucursal con funciones de supervivencia para proporcionar servicio telefónico en caso de que el vínculo WAN al sitio central dejara de funcionar. No obstante, el Sitio de sucursal 2 tiene un vínculo WAN resistente, de modo que solo necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada en este caso admite el desvío de medios, por lo que en el Sitio de sucursal B no es necesario ningún servidor de mediación. Para obtener más información sobre cómo decidir qué instalar en un sitio de sucursal, consulte [Planear la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación sobre planeamiento.

  - **Enlace troncal SIP y servidor de mediación.**   Observe que en el Sitio central B, el servidor de mediación no está instalado con los servidores front-end. Esto se debe a que el servidor de mediación independiente es recomendable para sitios que usen el enlace troncal SIP. En la mayoría de casos restantes, se recomienda instalar el servidor de mediación con el servidor front-end. Para obtener más información sobre las topologías de servidor de mediación, consulte [Componentes y topologías para el servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación sobre planeamiento.

  - **Chat persistente implementado.**   Esta organización ha implementado los servidores necesarios para habilitar Chat persistente. Ha implementado varios servidores front-end de Chat persistente para, por un lado, procesar la carga del número de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado Cumplimiento para Chat persistente y ha ubicado el Almacén de Chat persistente y el Almacén de Cumplimiento de Chat persistente en servidores aparte. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.

  - **Equilibrio de carga de DNS.**   Grupo de servidores front-end y el grupo de servidores perimetrales. De esta forma, no son necesarios equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que se debe invertir en la configuración y el mantenimiento de los equilibradores de carga de hardware para el resto de grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener información detallada sobre el equilibrio de carga de DNS, consulte [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación sobre planeamiento.

  - **Implementación de mensajería unificada de Exchange.**   Lync Server funciona tanto con implementaciones *locales* como *alojadas* de mensajería unificada de Exchange. El Sitio central A incluye un servidor de Mensajería unificada de Exchange (UM) que ejecuta Microsoft Exchange Server, en lugar de Lync Server. Las funciones de Mensajería unificada de Exchange para Lync Server se ejecutan en el grupo de servidores front-end.
    
    El Sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas.
    
    Para obtener información detallada sobre cómo usar Mensajería unificada de Exchange, consulte [Planear la integración de la mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Integración de la mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.

  - **Office Web Apps Server.**   Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Puede implementar una única granja de servidores de Office Web Apps Server en un sitio que sirva tráfico desde todos los sitios, o bien implementarla en cada sitio. Office Web Apps Server permite presentar diapositivas de PowerPoint en conferencias web. Para obtener más información, consulte [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Pueden agregarse Directores.**   Si esta organización deseara una mayor seguridad contra ataques por denegación de servicio, podría implementar también un grupo de servidores de Directores. Un Director es un rol de servidor opcional y aparte en Lync Server que no hospeda cuentas de usuario ni facilita servicios de presencia o conferencia. Sirve como servidor interno de próximo salto al que un Servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El Director preautentica las solicitudes entrantes y las redirige al servidor o grupo de servidores principales del usuario. La preautenticación en el Director permite omitir solicitudes de cuentas de usuario desconocidas en la implementación. Un Director ayuda a aislar a los servidores front-end del tráfico malintencionado, como son los ataques por denegación de servicio. Si la red se inunda de tráfico externo no válido en este tipo de ataque, dicho tráfico finalizará en el Director.

  - **Se ha implementado System Center Operations Manager.**   Se recomienda supervisar el estado de su implementación de Lync Server para garantizar la disponibilidad del servicio a los usuarios finales. Puede supervisar Lync con el módulo de administración de System Center Operations Manager para Lync, que puede obtener como descarga gratuita de Microsoft. Con el módulo de administración de Lync podrá obtener alertas proactivas en tiempo real cuando surjan problemas, ejecutar transacciones sintéticas para probar la funcionalidad de extremo a extremo de Lync, obtener informes de disponibilidad del servicio, etc. Esto le ayudará a responder proactivamente a problemas con su implementación antes de que los usuarios finales sufran las consecuencias.
    
    Esta organización tiene implementado un servidor System Center Operations Manager en cada sitio central.

