---
title: 'Lync Server 2013: Topología de referencia para pequeñas organizaciones'
TOCTitle: Topología de referencia para pequeñas organizaciones
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48274283
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topología de referencia en Lync Server 2013 para pequeñas organizaciones

 

_**Última modificación del tema:** 2013-10-07_

La topología de referencia para pequeñas organizaciones muestra cómo se puede implementar una solución robusta y de alta disponibilidad con la implementación solo de tres servidores que ejecuten Lync Server.

**Topología de referencia para pequeñas organizaciones**

![Diagrama de la topología de referencia con tres servidores implementados](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagrama de la topología de referencia con tres servidores implementados")

  - **Par de servidores Standard Edition implementados**    Esta organización tiene 4000 usuarios en su sitio central. La organización ha implementado dos servidores de Standard Edition que se usan emparejados para disponer de características de alta disponibilidad y recuperación ante desastres. Cada uno de los servidores hospeda 2000 usuarios, pero la información de todos ellos se sincroniza entre ambos servidores. Si uno de los servidores deja de funcionar, el administrador puede realizar una conmutación por error para que el otro servidor provea servicio a los usuarios, lo que redunda en un nivel de interrupción mínimo para ellos. Para más información sobre las características de alta disponibilidad y recuperación ante desastres de Lync Server 2013, vea [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Se recomienda la implementación de un servidor perimetral.**   Aunque no es necesaria la implementación de un servidor perimetral para la mensajería instantánea, la presencia y la conferencia, se recomienda efectuarla incluso en el caso de implementaciones pequeñas. Puede maximizar su inversión en Lync Server implementando un servidor perimetral que proporcione servicios a los usuarios que se encuentran actualmente fuera de las puertas de enlace de su organización. Entre las ventajas se incluye lo siguiente:
    
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


  - **Supervivencia de sucursales.**   Esta organización está ejecutando un programa piloto de la característica de Telefonía IP empresarial de Lync Server. Algunos usuarios usan Lync Server como única solución de voz. Algunos de estos usuarios piloto de voz se encuentran en una sucursal. La sucursal no dispone de vínculo de red de área extensa (WAN) fiable al sitio central, por lo que se ha implementado una Aplicación de sucursal con funciones de supervivencia. Gracias a esta implementación, si el vínculo WAN deja de funcionar, los usuarios de la sucursal podrán seguir haciendo y recibiendo llamadas (llamadas dentro de la organización y llamadas RTC), tener la funcionalidad de correo de voz y comunicarse mediante mensajería instantánea entre dos participantes. Los usuarios también pueden autenticarse cuando el vínculo WAN tampoco está disponible.

  - **Implementación de Mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de Mensajería unificada de Exchange (UM), que ejecuta Microsoft Exchange Server y no Lync Server.
    
    Para obtener información detallada sobre cómo usar Mensajería unificada de Exchange, consulte [Planear la integración de la mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Integración de la mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) en la documentación de planeación.

  - **Servidor de Office Web Apps** Se recomienda la implementación de un servidor de Office Web Apps o de una granja de servidores de Office Web Apps en todas las organizaciones que usen características de conferencia web. El servidor de Office Web Apps hace que sea posible la presentación de diapositivas de PowerPoint en conferencias web. Para más información, vea [Configuración de la integración de Office Web Apps Server y Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

