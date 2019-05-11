---
title: Topologías de referencia de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologías de referencia de Skype para Business Server, incluidos diagramas y decisiones que debe tomar grandes y medianas y las organizaciones pequeñas.
ms.openlocfilehash: 4cf7a33f06c3d181bc5213f67e19479665dbce6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895085"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologías de referencia de Skype para Business Server

Topologías de referencia de Skype para Business Server, incluidos diagramas y decisiones que debe tomar grandes y medianas y las organizaciones pequeñas.

La mejor Skype para la topología de servidores de negocio para depende del tamaño de su organización, las cargas de trabajo que desea implementar y las preferencias de alta disponibilidad frente a costo de la inversión.

En esta sección se describen tres topologías de referencia de ejemplo, además de la lógica que impera en muchas de las decisiones que determinan cada topología.

## <a name="reference-topology-for-a-small-organization"></a>Topología de referencia para una organización pequeña

La topología de referencia para pequeñas organizaciones muestra cómo se puede implementar una solución robusta y altamente disponible mediante la implementación de sólo tres servidores que ejecutan Skype para Business Server.

**Topología de referencia para pequeñas organizaciones**

![Diagrama de la topología de referencia con tres servidores implementados](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Par de servidores Standard Edition implementados** Esta organización tiene 4000 usuarios en su sitio central. Ha implementado dos servidores Standard Edition y emparejado para habilitar la alta disponibilidad y recuperación ante desastres. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Para obtener más información acerca de la alta disponibilidad y funciones de recuperación ante desastres en Skype para Business Server, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Recomendamos la implementación de un servidor perimetral.** Aunque no es necesaria la implementación de un servidor perimetral para la mensajería instantánea (MI), la presencia y la conferencia, recomendamos efectuarla incluso en el caso de implementaciones pequeñas. Puede maximizar su Skype para inversión Business Server mediante la implementación de un servidor perimetral para proporcionar servicio a los usuarios actualmente fuera de los servidores de seguridad de la organización. Entre las ventajas se incluye las siguientes:

  - Los usuarios de la organización pueden utilizar Skype para la funcionalidad del servidor empresarial, si trabajan desde casa o están de viaje.

  - Los usuarios pueden invitar a usuarios externos para participar en reuniones.

  - Si tiene un socio, el proveedor o la organización del cliente que también usa Skype para Business Server, puede formar una relación federada con esa organización. Su Skype para la implementación de Business Server podría reconocer, a continuación, los usuarios de esa organización federada, lo que lleva a una mejor colaboración.

  - Los usuarios pueden intercambiar mensajes instantáneos con usuarios de algunos servicios de mensajería instantánea (MI) pública.

- **Supervivencia de sitios de sucursal.** Esta organización se está ejecutando un programa piloto de la característica de Enterprise Voice de Skype para Business Server. Algunos usuarios usa Skype para Business Server como su solución de voz único. Algunos de estos usuarios pilotos de Enterprise Voice se encuentran en el sitio de sucursal. El sitio de sucursal no tiene un vínculo de confiable de área extensa (WAN) de red para el sitio central, por lo que una aplicación de sucursal con funciones de supervivencia se implementa no existe. Gracias a esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal podrán seguir realizando y recibiendo llamadas (llamadas dentro de la organización y llamadas RTC), disponer de la función del correo de voz y comunicarse por medio de la mensajería instantánea (MI) entre dos participantes. Los usuarios también pueden autenticarse cuando el vínculo WAN no está disponible. Para más información, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Implementación de la mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada de Exchange (UM), que se ejecuta Microsoft Exchange Server, no Skype para Business Server.

- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.

## <a name="reference-topology-for-a-medium-organization"></a>Topología de referencia para una organización mediana

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del diagrama siguiente es para una organización de 20 000 usuarios.

**Topología de referencia para organizaciones medianas**

![Diagrama de la topología de referencia para un solo centro de datos](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Incluya más usuarios al agregar más servidores front-end.** La topología exacta de este diagrama tiene tres servidores front-end para proporcionar compatibilidad para 20 000 usuarios. Si dispone de un único sitio central y más usuarios, solo tiene que agregar más servidores front-end al grupo de servidores. La cantidad máxima de usuarios por grupo de servidores es de 80 000, con doce servidores front-end.

    Pero, la topología de sitio único puede admitir incluso más usuarios si se agrega otro grupo de servidores front-end al sitio.

- **Es posible agregar la recuperación ante desastres.** Para esta organización, una alta disponibilidad para su Skype para servicios de Business Server es una característica es necesaria, pero no es de recuperación ante desastres. El grupo de servidores Front-End que han implementado proporciona una alta disponibilidad.

    Si desearan agregar la capacidad de recuperación ante desastres, podrían pensar en establecer otro centro de datos y agregar allí otro grupo de servidores front-end y vincularlo con el grupo de servidores front-end de su centro de datos actual. Luego, si se produjera un desastre que afectara al grupo principal, los administradores podrían realizar la conmutación por error de los usuarios al grupo de copia de seguridad.

- **Se reflejan los servidores Back-End** Para proporcionar más alta disponibilidad para las características de usuario básica, la organización ha implementado un par reflejado de servidores Back-End para cada grupo de servidores Front-End.

- **Opciones de bases de datos del servidor de supervisión.** Esta organización ha implementado supervisión para garantizar la calidad de las llamadas de telefonía IP empresarial y A / conferencias A/v. La supervisión se implementa en cada servidor front-end y la base de datos de supervisión se combina con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.

- **Servidor perimetral de alta disponibilidad** En este ejemplo de organización con 20.000 usuarios, sería suficiente para obtener un rendimiento un solo servidor perimetral. Pero, se ha implementado un grupo de dos servidores perimetrales para proporcionar alta disponibilidad.

- **Opciones de implementación de sitios de sucursal.** La organización en esta topología tiene implementado como su solución de voz de Enterprise Voice. Sitio de sucursal 1 no tiene un vínculo de resistente de área extensa (WAN) para el sitio central, por lo que tiene una aplicación de sucursal con funciones de supervivencia implementa para mantener que Skype muchas de las características de Business Server en caso de que el vínculo WAN al sitio central deja de funcionar. Pero, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite la omisión de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para más información, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales tienen implementado el equilibrio de carga de DNS para el tráfico SIP. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la instalación y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para obtener más información, vea (.. /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de mensajería unificada de Exchange (UM), que se ejecuta Microsoft Exchange Server, no Skype para Business Server.

- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.

- **Es posible agregar directores.** Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un Director es una función de servidor independiente, opcional de Skype para Business Server que no hospeda las cuentas de usuario, o proporcionar servicios de presencia o conferencia. Actúa como un servidor interno de salto siguiente a la que un servidor perimetral enruta el tráfico SIP entrante dirigido a los servidores internos. El Director autentica las solicitudes entrantes y las redirige a servidor o grupo de servidores principal del usuario. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un Director ayuda a aislar los servidores Front-End del tráfico malintencionado como ataques de denegación de servicio (DoS). Si la red se desborda con el tráfico externo no válido en este tipo de ataque, el tráfico se termina en el Director.

- **Se recomienda System Center Operations Manager.** Se recomienda que supervisar el estado de su Skype para la implementación de Business Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede usar el módulo de administración de System Center Operations Manager para Skype para la empresa que está disponible como una descarga gratuita de Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.

## <a name="reference-topology-for-a-large-organization"></a>Topología de referencia para una organización de gran tamaño

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el sitio central A, 20 000 en el sitio central B y un total de 10 000 en el sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con cualquier cantidad de usuarios.

Además de la alta disponibilidad proporcionada por los grupos de servidores Front-End, esta topología agrega compatibilidad con la recuperación ante desastres. Los grupos de servidores Front-End de sitios centrales A y B están emparejados juntos. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá cambiar los servicios de los usuarios afectados al grupo emparejado en el sitio no afectado.

Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.

**Información general de la topología de referencia para organizaciones de gran tamaño con varios centros de datos**

![Topología de referencia para varios centros de datos](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central A**

![Topología 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central B**

![Topología 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central C**

![Topología 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Grupos de servidores Front-End están emparejados para habilitar la recuperación ante desastres.** Los grupos de servidores Front-End en el sitio A y el sitio B están emparejados con cada una de las demás, para proporcionar compatibilidad con la recuperación ante desastres. Si se produce un error en el grupo de servidores en un sitio, el administrador puede conmutar por los usuarios de ese sitio al grupo de servidores Front-End emparejado en el sitio, con un mínimo de interrupción del servicio para los usuarios. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Para obtener más información, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Se reflejan los servidores Back-End** Para proporcionar más alta disponibilidad para las características de usuario básica, la organización ha implementado un par reflejado de servidores Back-End para cada grupo de servidores Front-End. Ésta es una topología opcional y puede optar por implementar un único servidor Back-End en su lugar. SQL clustering and AlwaysOn Availability groups are also supported. For more information, see [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Uso de un servidor Standard Edition en un sitio de sucursal.** This organization considers Site C as a branch site because it has only 600 employees. However, the users there have many A/V conferences among themselves. Si se implementó en Skype para Business Server como un sitio de sucursal, los medios para estas conferencias tendría que ejecutar a través de la red de área extensa (WAN) a y desde un sitio central que tiene un servidor Front-End implementados. Para evitar esta carga de ancho de banda posibles, ha instalado a un par de servidores Standard Edition en este sitio, que se va a hospedar estas conferencias. Y ya que se instalan los servidores Standard Edition allí, Skype para Business Server según la definición de lo considera un sitio central y se trata como tal en el generador de topología y la herramienta de planeación.

    Un solo servidor Standard Edition puede ofrecer suficiente rendimiento aquí, pero la organización ha implementado dos y emparejado para proporcionar una alta disponibilidad en caso de que un servidor deja de funcionar.

    A pesar de que el sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el sitio C usará los servidores perimetrales implementados en el sitio A.

- **Supervisión y archivado** Esta organización ha implementado supervisión y archivado. Si se implementa la supervisión o el archivado, se ejecutarán en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end, o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el sitio central B. Las bases de datos de esta ubicación reciben datos de supervisión y archivado desde los servidores front-end de todos los sitios.

- **Opciones de implementación en sitios de sucursal.** Esta organización tiene en realidad más de 50 sitios de sucursal y, en los diagramas detallados, solo se muestran dos de ellos. Sitio de sucursal 1 no tiene una WAN resistente vínculo al sitio central, por lo que tienen aplicaciones de sucursal con funciones de supervivencia implementa para proporcionar el servicio de teléfono en caso de que el vínculo WAN al sitio central deja de funcionar. Pero, el sitio de sucursal 2 sí tiene un vínculo WAN resistente, de modo que solo necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada en este caso admite la omisión de medios, por lo que en el sitio de sucursal 2 no es necesario ningún servidor de mediación. Para más detalles sobre cómo decidir qué instalar en un sitio de sucursal, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Enlace troncal SIP y el servidor de mediación.** Tenga en cuenta que en el sitio Central B, el servidor de mediación no se combina con el servidor front-end. Esto es debido a que el servidor de mediación independiente se recomienda para sitios que usan el enlace troncal SIP. En la mayoría de los demás casos, se recomienda que instalar el servidor de mediación con el servidor Front-End. Para obtener información detallada acerca de las topologías de servidor de mediación, vea [componentes y topologías de servidor de mediación](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) en la documentación de planeación.

- **Chat persistente implementado.** Esta organización ha implementado los servidores necesarios para habilitar el chat persistente. Ha implementado varios servidores front-end de chat persistente para, por un lado, procesar la carga de la cantidad de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado el cumplimiento para el chat persistente y ha ubicado el almacén de chat persistente y el almacén de cumplimiento de chat persistente en servidores independientes. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.

    > [!NOTE]
    > Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.

- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales utilizan el equilibrio de carga de DNS. De esta manera, no son necesarios los equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que necesaria para la instalación y el mantenimiento de los equilibradores de carga de hardware para el resto de los grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener más información, vea (.. /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implementación de mensajería unificada de Exchange.** Skype para Business Server funciona con ambas implementaciones locales de Exchange mensajería unificada (MU) y mensajería unificada de Exchange hospedado. Sitio central A incluye un servidor de mensajería unificada de Exchange (UM), que se ejecuta Microsoft Exchange Server, no Skype para Business Server. La funcionalidad de mensajería unificada de Exchange para Skype para Business Server se ejecuta en el grupo de servidores Front-End.

    El sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas.

    Para obtener información detallada acerca de la mensajería unificada de Exchange, consulte [Local Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) y [Hosted Exchange Unified Messaging Integration](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) en la documentación de planeación.

- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. Puede implementar una granja de servidores de Office Web Apps Server único en un sitio que sirve el tráfico de todos los sitios, o implementar en cada sitio. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.

- **Es posible agregar directores.** Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un Director es una función de servidor independiente, opcional de Skype para Business Server que no hospeda las cuentas de usuario, o proporcionar servicios de presencia o conferencia. Actúa como un servidor interno de salto siguiente a la que un servidor perimetral enruta el tráfico SIP entrante dirigido a los servidores internos. El Director autentica las solicitudes entrantes y las redirige a servidor o grupo de servidores principal del usuario. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un Director ayuda a aislar los servidores Front-End del tráfico malintencionado como ataques de denegación de servicio (DoS). Si la red se desborda con el tráfico externo no válido en este tipo de ataque, el tráfico se termina en el Director.

- **Se recomienda System Center Operations Manager.** Se recomienda que supervisar el estado de su Skype para la implementación de Business Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede usar el módulo de administración de System Center Operations Manager para Skype para la empresa que está disponible como una descarga gratuita de Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.


