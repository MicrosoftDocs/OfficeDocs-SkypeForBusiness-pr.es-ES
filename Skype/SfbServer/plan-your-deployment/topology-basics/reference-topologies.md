---
title: Topologías de referencia para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologías de referencia para Skype empresarial Server, incluidos diagramas y decisiones para organizaciones grandes, medianas y pequeñas.
ms.openlocfilehash: f207e69dceea4c2959e5cf81ddcf359266ed1604
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801710"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologías de referencia para Skype empresarial Server

Topologías de referencia para Skype empresarial Server, incluidos diagramas y decisiones para organizaciones grandes, medianas y pequeñas.

La mejor topología de Skype empresarial Server depende del tamaño de su organización, las cargas de trabajo que desea implementar y las preferencias de alta disponibilidad frente al costo de la inversión.

En esta sección se describen tres topologías de referencia de ejemplo, además de la lógica que impera en muchas de las decisiones que determinan cada topología.

## <a name="reference-topology-for-a-small-organization"></a>Topología de referencia para una organización pequeña

La topología de referencia para organizaciones pequeñas muestra cómo puede implementar una solución robusta y de alta disponibilidad implementando solo tres servidores que ejecuten Skype empresarial Server.

**Topología de referencia para pequeñas organizaciones**

![Diagrama de la topología de referencia con tres servidores implementados](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Par de servidores Standard Edition implementados** Esta organización tiene usuarios de 4.000 en su sitio central. Han implementado dos servidores Standard Edition y los ha emparejado para habilitar la alta disponibilidad y la recuperación ante desastres. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Para obtener más información sobre las características de alta disponibilidad y recuperación ante desastres de Skype empresarial Server, consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Recomendamos la implementación de un servidor perimetral.** Aunque no es necesaria la implementación de un servidor perimetral para la mensajería instantánea (MI), la presencia y la conferencia, recomendamos efectuarla incluso en el caso de implementaciones pequeñas. Puede maximizar la inversión de Skype empresarial Server implementando un servidor perimetral para proporcionar servicio a los usuarios que se encuentran fuera de los firewalls de su organización. Entre las ventajas se incluye las siguientes:

  - Los usuarios de su organización pueden usar la funcionalidad de Skype empresarial Server, si están trabajando desde casa o están de viaje.

  - Los usuarios pueden invitar a usuarios externos para participar en reuniones.

  - Si tiene una organización de socios, proveedores o clientes que también usa Skype empresarial Server, puede formar una relación federada con esa organización. Su implementación de Skype empresarial Server entonces reconocería a los usuarios de esa organización federada, lo que lleva a una mejor colaboración.

  - Los usuarios pueden intercambiar mensajes instantáneos con usuarios de algunos servicios de mensajería instantánea (MI) pública.

- **Supervivencia de sitios de sucursal.** Esta organización está ejecutando un programa piloto de la característica de telefonía IP empresarial de Skype empresarial Server. Algunos usuarios usan Skype empresarial Server como una única solución de voz. Algunos de estos usuarios de Enterprise Voice Pilot se encuentran en el sitio de la sucursal. El sitio de la sucursal no tiene un vínculo de red de área extensa (WAN) confiable al sitio central para que se implemente en él un dispositivo de sucursal con la supervivencia. Gracias a esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal podrán seguir realizando y recibiendo llamadas (llamadas dentro de la organización y llamadas RTC), disponer de la función del correo de voz y comunicarse por medio de la mensajería instantánea (MI) entre dos participantes. Los usuarios también pueden autenticarse cuando el vínculo WAN no está disponible. Para más información, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Implementación de la mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Skype empresarial Server.

- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.

## <a name="reference-topology-for-a-medium-organization"></a>Topología de referencia para una organización mediana

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del diagrama siguiente es para una organización de 20 000 usuarios.

**Topología de referencia para organizaciones medianas**

![Diagrama de la topología de referencia para un solo centro de datos](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Incluya más usuarios al agregar más servidores front-end.** La topología exacta de este diagrama tiene tres servidores front-end para proporcionar compatibilidad para 20 000 usuarios. Si dispone de un único sitio central y más usuarios, solo tiene que agregar más servidores front-end al grupo de servidores. La cantidad máxima de usuarios por grupo de servidores es de 80 000, con doce servidores front-end.

    Pero, la topología de sitio único puede admitir incluso más usuarios si se agrega otro grupo de servidores front-end al sitio.

- **Es posible agregar la recuperación ante desastres.** Para esta organización, la alta disponibilidad de los servicios de Skype empresarial es una característica necesaria, pero no la de recuperación ante desastres. El grupo de servidores front-end que ha implementado proporciona alta disponibilidad.

    Si desearan agregar la capacidad de recuperación ante desastres, podrían pensar en establecer otro centro de datos y agregar allí otro grupo de servidores front-end y vincularlo con el grupo de servidores front-end de su centro de datos actual. Luego, si se produjera un desastre que afectara al grupo principal, los administradores podrían realizar la conmutación por error de los usuarios al grupo de copia de seguridad.

- **Los servidores de back-end están reflejados** Para proporcionar una mayor disponibilidad para las características básicas de usuario, la organización ha implementado un par simétrico de servidores back-end para cada grupo de servidores front-end.

- **Opciones de bases de datos del servidor de supervisión.** Esta organización ha implementado la supervisión para garantizar la calidad de las llamadas de voz de empresa y las conferencias A/V. La supervisión se implementa en cada servidor front-end y la base de datos de supervisión se combina con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.

- **Alta disponibilidad del servidor perimetral** En esta organización de ejemplo con usuarios de 20.000, solo un servidor perimetral sería suficiente para el rendimiento. Pero, se ha implementado un grupo de dos servidores perimetrales para proporcionar alta disponibilidad.

- **Opciones de implementación de sitios de sucursal.** La organización de esta topología tiene la característica telefonía IP implementada como solución de voz. El sitio de la sucursal 1 no tiene un vínculo de red de área extensa (WAN) resistente al sitio central, por lo que tiene un dispositivo de sucursal que se ha implementado y que mantiene muchas características de Skype empresarial Server en caso de que se produzca un vínculo WAN al sitio central. Pero, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite la omisión de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para más información, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales tienen implementado el equilibrio de carga de DNS para el tráfico SIP. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la instalación y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para obtener más información, consulte [equilibrio de carga de DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Skype empresarial Server.

- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.

- **Es posible agregar directores.** Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor independiente y opcional en Skype empresarial Server que no aloja las cuentas de usuario o proporciona servicios de presencia o de conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al grupo de servidores o al grupo de servidores domésticos del usuario. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un director ayuda a aislar a los servidores front-end de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red se inunda con tráfico externo no válido en tal ataque, el tráfico termina en el director.

- **Se recomienda System Center Operations Manager.** Le recomendamos que supervise el estado de su implementación de Skype empresarial Server para garantizar la disponibilidad del servicio para los usuarios finales. Puede usar el paquete de administración de System Center Operations Manager para Skype empresarial, que está disponible como descarga gratuita de Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.

## <a name="reference-topology-for-a-large-organization"></a>Topología de referencia para una organización de gran tamaño

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el sitio central A, 20 000 en el sitio central B y un total de 10 000 en el sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con cualquier cantidad de usuarios.

Además de la alta disponibilidad proporcionada por los grupos de servidores de aplicaciones para el usuario, esta topología agrega compatibilidad de recuperación ante desastres. Los grupos front-end de los sitios centrales A y B están emparejados. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá cambiar los servicios de los usuarios afectados al grupo emparejado en el sitio no afectado.

Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.

**Información general de la topología de referencia para organizaciones de gran tamaño con varios centros de datos**

![Topología de referencia para varios centros de datos](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central A**

![Topología 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central B**

![Topología 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central C**

![Topología 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Los grupos de servidores front-end se emparejan para habilitar la recuperación ante desastres.** Los grupos de aplicaciones para el usuario del sitio A y el sitio B están emparejados entre sí, para proporcionar compatibilidad con la recuperación ante desastres. Si se produce un error en el grupo de un sitio, el administrador puede migrar por error los usuarios de ese sitio a la agrupación front-end del otro sitio, con una interrupción mínima de servicio para los usuarios. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Para obtener más información, consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Los servidores de back-end están reflejados** Para proporcionar una mayor disponibilidad para las características básicas de usuario, la organización ha implementado un par simétrico de servidores back-end para cada grupo de servidores front-end. Esta es una topología opcional y puede optar por implementar un único servidor de servicios de fondo en su lugar. SQL clustering and AlwaysOn Availability groups are also supported. For more information, see [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Usar un servidor Standard Edition en un sitio de sucursal.** This organization considers Site C as a branch site because it has only 600 employees. However, the users there have many A/V conferences among themselves. Si se ha implementado en Skype empresarial Server como sitio de sucursal, los medios de estas conferencias se ejecutarán en la red de área extensa (WAN) a y desde un sitio central que tiene un servidor front-end implementado. Para evitar esta carga potencial de ancho de banda, han instalado un par de servidores Standard Edition en este sitio, que hospedarán estas conferencias. Y como los servidores Standard Edition están instalados allí, Skype empresarial Server por definición lo considera un sitio central y se trata como tal en el generador de topologías y la herramienta de planificación.

    Solo un servidor Standard Edition sería suficiente para el rendimiento, pero la organización ha implementado dos y los ha emparejado para ofrecer alta disponibilidad en caso de que un servidor se quede sin funcionar.

    A pesar de que el sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el sitio C usará los servidores perimetrales implementados en el sitio A.

- **Supervisar y archivar** Esta organización ha implementado la supervisión y el archivado. Si se implementa la supervisión o el archivado, se ejecutarán en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end, o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el sitio central B. Las bases de datos de esta ubicación reciben datos de supervisión y archivado desde los servidores front-end de todos los sitios.

- **Opciones de implementación en sitios de sucursal.** Esta organización tiene en realidad más de 50 sitios de sucursal y, en los diagramas detallados, solo se muestran dos de ellos. El sitio de la sucursal 1 no tiene un vínculo WAN resistente al sitio central, por lo que se han implementado dispositivos de sucursal que se han implementado para proporcionar servicio telefónico en caso de que se produzca un vínculo WAN al sitio central. Pero, el sitio de sucursal 2 sí tiene un vínculo WAN resistente, de modo que solo necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada en este caso admite la omisión de medios, por lo que en el sitio de sucursal 2 no es necesario ningún servidor de mediación. Para más detalles sobre cómo decidir qué instalar en un sitio de sucursal, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Servidor de mediación y Troncalización SIP.** Observe que en el sitio central B, el servidor de mediación no se colocará con los servidores front-end. Esto se debe a que se recomienda un servidor de mediación independiente para los sitios que usan Troncalización SIP. En la mayoría de las demás instancias, le recomendamos que Collocate servidor de mediación con el servidor front-end. Para obtener más información sobre las topologías de servidores de mediación, vea [componentes y topologías de servidor de mediación](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) en la documentación de planeación.

- **Chat persistente implementado.** Esta organización ha implementado los servidores necesarios para habilitar el chat persistente. Ha implementado varios servidores front-end de chat persistente para, por un lado, procesar la carga de la cantidad de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado el cumplimiento para el chat persistente y ha ubicado el almacén de chat persistente y el almacén de cumplimiento de chat persistente en servidores independientes. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.

    > [!NOTE]
    > Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.

- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales utilizan el equilibrio de carga de DNS. De esta manera, no son necesarios los equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que necesaria para la instalación y el mantenimiento de los equilibradores de carga de hardware para el resto de los grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener más información, consulte (.. /.. /Plan-Your-Deployment/Network-requirements/Load-Balancing.MD # BKMK_DNSLoadBalancing).

- **Implementación de mensajería unificada de Exchange.** Skype empresarial Server funciona con las implementaciones locales de mensajería unificada de Exchange (UM) y la mensajería unificada de Exchange hospedada. El sitio central A incluye un servidor de mensajería unificada (UM) de Exchange, que ejecuta Microsoft Exchange Server, no Skype empresarial Server. La funcionalidad de mensajería unificada de Exchange para Skype empresarial Server se ejecuta en el grupo de servidores front-end.

    El sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas.

    Para obtener más información sobre la mensajería unificada de Exchange, consulte [integración de mensajería unificada local de Exchange](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) y [integración de mensajería unificada de Exchange hospedada](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) en la documentación de planeación.

- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. Puede implementar una sola granja de Office Web Apps Server en un sitio que sirva de tráfico de todos los sitios o implementarla en cada sitio. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.

- **Es posible agregar directores.** Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor independiente y opcional en Skype empresarial Server que no aloja las cuentas de usuario o proporciona servicios de presencia o de conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a los servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al grupo de servidores o al grupo de servidores domésticos del usuario. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un director ayuda a aislar a los servidores front-end de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red se inunda con tráfico externo no válido en tal ataque, el tráfico termina en el director.

- **Se recomienda System Center Operations Manager.** Le recomendamos que supervise el estado de su implementación de Skype empresarial Server para garantizar la disponibilidad del servicio para los usuarios finales. Puede usar el paquete de administración de System Center Operations Manager para Skype empresarial, que está disponible como descarga gratuita de Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.


