---
title: "Topo. de réf. de Lync Server 2013 pour les organisations de taille moyenne"
TOCTitle: Topología de referencia para organizaciones medianas
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48275070
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topología de referencia para organizaciones medianas en Lync Server 2013

 

_**Última modificación del tema:** 2013-10-07_

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del diagrama siguiente es para una organización de 20.000 usuarios.

**Topología de referencia para organizaciones medianas**

![Diagrama de la topología de referencia para un solo centro de datos](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Diagrama de la topología de referencia para un solo centro de datos")

  - **Incluya más usuarios mediante la incorporación de más servidores front-end.**   La topología exacta de este diagrama tiene tres servidores front-end para proporcionar compatibilidad para 20.000 usuarios. Si dispone de un único servidor central y más usuarios, solo tiene que agregar más servidores front-end al grupo de servidores. El número máximo de usuarios por grupo de servidores es de 80.000, con doce servidores front-end.
    
    Sin embargo, la topología de sitio único puede admitir aún más usuarios si se agrega otro grupo de servidores front-end al sitio.

  - **Se podría agregar la recuperación ante desastres.**   Para esta organización, la alta disponibilidad de servicios de Lync Server es una característica necesaria, pero no lo es la recuperación ante desastres. El grupo de Servidores front-end que han implementado proporciona alta disponibilidad.
    
    Si desearan agregar capacidad de recuperación ante desastres, podrían pensar en establecer otro centro de datos y agregar allí otro grupo front-end y vincularlo con el grupo front-end de su centro de datos actual. Luego, si se produjera un desastre que afectara a su grupo principal, los administradores podrían realizar la conmutación por error de los usuarios al grupo de copia de seguridad.

  - **Servidores back-end están reflejadas**   Para proporcionar disponibilidad más alta para las funciones básicas de usuario, la organización ha implementado un par reflejado de Servidores back-end para cada Grupo de servidores front-end. Es una nueva opción de topología para Lync Server 2013 y es opcional. En su lugar, podría elegir la implementación de un solo Servidor back-end.

  - **Opciones de base de datos de Servidor de supervisión.**   Esta organización ha implementado la supervisión para garantizar la calidad de las llamadas de Telefonía IP empresarial y las conferencias A/V. La supervisión se implementa en cada servidor front-end y la base de datos de supervisión se coloca con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.

  - **Alta disponibilidad de servidor perimetral.**   En este ejemplo de organización con 20.000 usuarios, debería bastar con un servidor perimetral para obtener un buen rendimiento. Sin embargo, hay implementado un grupo de dos servidores perimetrales para proporcionar una alta disponibilidad.

  - **Opciones de implementación en sitios de sucursal.**   La organización de esta topología ha implementado la Telefonía IP empresarial como su solución de voz. El sitio de sucursal 1 no dispone de ningún vínculo de red de área extensa (WAN) resistente al sitio central, por lo que ha implementado la Aplicación de sucursal con funciones de supervivencia para mantener muchas características de Lync Server en el caso de que el vínculo WAN al sitio central deje de funcionar. Sin embargo, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite el desvío de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para obtener información detallada acerca de cómo decidir qué implementar en un sitio de sucursal, consulte [Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) en la documentación referente a la planeación.

  - **Equilibrio de carga de DNS.**   El grupo de servidores front-end y el grupo de servidores perimetrales tienen implementado un equilibrio de carga de DNS para el tráfico SIP. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la configuración y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para información detallada sobre el equilibrio de carga de DNS, vea [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación sobre planificación.

  - **Implementación de Mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de Mensajería unificada de Exchange (UM), que ejecuta Microsoft Exchange Server y no Lync Server.
    
    Para obtener información detallada sobre cómo usar Mensajería unificada de Exchange, consulte [Planear la integración de la mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Integración de la mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.

  - **Servidor de aplicaciones web de Office.** Recomendamos implementar un servidor de aplicaciones web de Office o una granja de servidores de aplicaciones web de Office en cada organización que use conferencias web. El servidor de aplicaciones web de Office permite presentar diapositivas de PowerPoint en conferencias web. Para más información, vea [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Se recomiendan servidores perimetrales.**   Aunque no es necesario implementar un servidor perimetral, sí es aconsejable para cualquier tamaño de implementación. Puede maximizar su inversión en Lync Server implementando un servidor perimetral que proporcione servicios a los usuarios que se encuentran actualmente fuera de las puertas de enlace de su organización. Entre las ventajas se incluye lo siguiente:
    
      - Los propios usuarios de su organización pueden usar la funcionalidad de Lync Server si trabajan desde casa o están de viaje.
    
      - Sus usuarios pueden invitar a usuarios externos para participar en reuniones.
    
      - Si tiene una organización que también usa Lync Server como socio, proveedor o cliente, puede crear una *relación asociada externa* con dicha organización. De este modo, su implementación de Lync Server reconocerá a los usuarios de dicha organización asociada externa, mejorando así la colaboración.
    
      - Sus usuarios pueden intercambiar mensajes instantáneos con usuarios de servicios de mensajería instantánea pública, entre los que se incluyen: Windows Live, AOL, Yahoo\! y Google Talk. Quizá sea necesaria otra licencia para la conectividad de mensajería instantánea pública con estos servicios.
        
        > [!IMPORTANT]  
		> <ul>
        > <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
        > <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
        > <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
        > </ul>


  - **Podrían agregarse directores.**   Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un Director es un rol del servidor opcional e independiente en Lync Server que no tiene cuentas de usuario particular ni proporciona servicios de presencia o conferencias. Sirve como un servidor interno de próximo salto al que un Servidor perimetral enruta el tráfico SIP de entrada destinado a los servidores internos. El Director realiza una autenticación previa de las solicitudes de entrada y las redirige al servidor a al grupo de usuarios particulares. La autenticación previa en el Director permite soltar las solicitudes de cuentas de usuario desconocidos para la implementación. Un Director ayuda a aislar servidores front-end del tráfico malintencionado como los ataques por denegación de servicio (DoS). Si la red se congestiona con tráfico externo no válido como en un ataque, el tráfico termina en el Director.

  - **Recomendamos System Center Operations Manager.**   Recomendamos que supervise el mantenimiento de su implementación de Lync Server para asegurar la disponibilidad del servicio para los usuarios finales. Puede supervisar Lync con el System Center Operations Manager Management Pack para Lync disponible como descarga gratuita de Microsoft. En Lync Management Pack, puede recibir alertas en tiempo real de forma proactiva cuando se producen problemas, ejecutar transacciones sintéticas para probar todas las funciones de Lync, recibir informes de disponibilidad del servicio, etc. Esto le ayudará a responder de forma proactiva a los problemas con la implementación antes de que los experimenten los usuarios finales.

