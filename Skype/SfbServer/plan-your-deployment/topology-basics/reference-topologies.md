---
title: Topologías de referencia para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologías de referencia para Skype Empresarial Server, incluidos diagramas y decisiones que se deben tomar para organizaciones grandes, medianas y pequeñas.
ms.openlocfilehash: 1f6598415627ca48181a6346007704536163ea94
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729759"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologías de referencia para Skype Empresarial Server

Topologías de referencia para Skype Empresarial Server, incluidos diagramas y decisiones que se deben tomar para organizaciones grandes, medianas y pequeñas.

La mejor topología Skype Empresarial Server para usted depende del tamaño de su organización, las cargas de trabajo que desea implementar y sus preferencias de alta disponibilidad frente al costo de la inversión.

En esta sección se describen tres topologías de referencia de ejemplo, incluido el razonamiento detrás de muchas de las decisiones que se tomaron en cada topología.

## <a name="reference-topology-for-a-small-organization"></a>Topología de referencia para una organización pequeña

La topología de referencia para organizaciones pequeñas muestra cómo implementar una solución sólida y de alta disponibilidad mediante la implementación de solo tres servidores que ejecutan Skype Empresarial Server.

**Topología de referencia para organizaciones pequeñas**

![Topología de referencia que implementa el diagrama de tres servidores.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Par de servidores Standard Edition implementados** Esta organización tiene 4.000 usuarios en su sitio central. Han implementado dos servidores Standard Edition y los han emparejado para habilitar la alta disponibilidad y la recuperación ante desastres. Cada servidor tiene 2.000 usuarios, pero la información sobre todos los usuarios está sincronizada entre los dos servidores. Si uno cae, un administrador puede conmutar por error a esos usuarios para que el otro servidor los pueda servir, con un mínimo de interrupción para los usuarios. Para obtener más información sobre la alta disponibilidad y las características de recuperación ante desastres en Skype Empresarial Server, vea [Plan for high availability and disaster recovery in Skype Empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Se recomienda la implementación de un servidor perimetral.** Aunque no es necesaria la implementación de un servidor perimetral para la mensajería instantánea, la presencia y la conferencia, se recomienda efectuarla incluso en el caso de implementaciones pequeñas. Puede maximizar la inversión Skype Empresarial Server mediante la implementación de un servidor perimetral para proporcionar servicio a los usuarios que actualmente están fuera de los firewalls de la organización. Entre las ventajas se incluye lo siguiente:

  - Los propios usuarios de la organización pueden usar Skype Empresarial Server funcionalidad, si trabajan desde casa o están de viaje.

  - Sus usuarios pueden invitar a usuarios externos para participar en reuniones.

  - Si tiene un partner, proveedor o organización de clientes que también usa Skype Empresarial Server, puede formar una relación federada con esa organización. La implementación Skype Empresarial Server reconocería a los usuarios de esa organización federada, lo que daría lugar a una mejor colaboración.

  - Los usuarios pueden intercambiar mensajes instantáneos con usuarios de algunos servicios de mensajería instantánea públicos.

- **Supervivencia de sucursales.** Esta organización ejecuta un programa piloto de la Telefonía IP empresarial de Skype Empresarial Server. Algunos usuarios usan Skype Empresarial Server como su única solución de voz. Algunos de estos Telefonía IP empresarial usuarios piloto se encuentran en el sitio de sucursal. El sitio de sucursal no tiene un vínculo de red de área extensa (WAN) confiable al sitio central, por lo que se implementa allí una aplicación de sucursal con funciones de supervivencia. Con esta implementación, si el vínculo WAN desaparece, los usuarios del sitio de sucursal aún pueden realizar y recibir llamadas (tanto llamadas dentro de la organización como llamadas RTC), tener funcionalidad de correo de voz y comunicarse con mensajería instantánea (MI) de dos partes. Los usuarios también pueden autenticarse cuando el vínculo WAN tampoco está disponible. Para obtener más información, vea [Plan for Telefonía IP empresarial resiliency in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un Exchange de mensajería unificada (MU), que se ejecuta Microsoft Exchange Server, no Skype Empresarial Server.

- **Office Web Apps Server.** Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Office Web Apps Server permite que PowerPoint diapositivas se presenten en conferencias web.

## <a name="reference-topology-for-a-medium-organization"></a>Topología de referencia para una organización mediana

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del siguiente diagrama es para una organización de 20.000 usuarios.

**Topología de referencia para organizaciones medianas**

![Topología de referencia para un solo diagrama de centro de datos.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Incluya más usuarios mediante la incorporación de más servidores front-end.** La topología exacta de este diagrama tiene tres servidores front-end para dar soporte a 20.000 usuarios. Si tiene un único sitio central y más usuarios, simplemente puede agregar más servidores front-end al grupo. El número máximo de usuarios por grupo es de 80.000, con doce servidores front-end.

    Sin embargo, la topología de sitio único puede admitir aún más usuarios si se agrega otro grupo de servidores front-end al sitio.

- **Se puede agregar la recuperación ante desastres.** Para esta organización, la alta disponibilidad para sus servicios Skype Empresarial Server es una característica necesaria, pero la recuperación ante desastres no lo es. El grupo de servidores front-end que han implementado proporciona alta disponibilidad.

    Si querían agregar la capacidad de recuperación ante desastres, podrían considerar la posibilidad de establecer otro centro de datos y agregar otro grupo de servidores front-end allí y emparejar con el grupo de servidores front-end en su centro de datos actual. A continuación, si hubiera un desastre que afectara a su grupo de servidores principal, los administradores podrían conmutar por error a los usuarios en el grupo de copia de seguridad.

- **Los servidores back-end se reflejan** Para proporcionar más alta disponibilidad para las características básicas del usuario, la organización ha implementado un par reflejado de servidores back-end para cada grupo de servidores front-end.

- **Opciones de bases de datos del Servidor de supervisión.** Esta organización ha implementado la supervisión para garantizar la calidad de las Telefonía IP empresarial llamadas y conferencias A/V. La supervisión se implementa en todos los servidores front-end y la base de datos de supervisión se coloca con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.

- **Alta disponibilidad del servidor perimetral** En este ejemplo de organización con 20.000 usuarios, solo un servidor perimetral sería suficiente para el rendimiento. Sin embargo, han implementado un grupo de dos servidores perimetrales implementados para proporcionar alta disponibilidad.

- **Opciones de implementación en sitios de sucursal.** La organización de esta topología ha implementado Enterprise Voice como su solución de voz. El sitio de sucursal 1 no tiene un vínculo de red de área extensa (WAN) resistente al sitio central, por lo que tiene implementada una aplicación de sucursal con funciones de supervivencia para mantener muchas características de Skype Empresarial Server en caso de que el vínculo WAN al sitio central se desvanee. Sin embargo, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite el desvío de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para obtener más información, vea [Plan for Telefonía IP empresarial resiliency in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales tienen el equilibrio de carga DNS para el tráfico SIP implementado. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la configuración y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para obtener más información, vea [Equilibrio de carga DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un Exchange de mensajería unificada (MU), que se ejecuta Microsoft Exchange Server, no Skype Empresarial Server.

- **Office Web Apps Server.** Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Office Web Apps Server permite presentar diapositivas de PowerPoint en conferencias web.

- **Pueden agregarse Directores.** Si esta organización quisiera ayudar a aumentar la seguridad frente a ataques de denegación de servicio, también podría implementar un grupo de directores. Un director es un rol de servidor independiente y opcional en Skype Empresarial Server que no tiene cuentas de usuario principales ni proporciona servicios de presencia o conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al servidor o grupo de servidores principal del usuario. La preautenticación en el Director permite omitir solicitudes de cuentas de usuario desconocidas en la implementación. Un director ayuda a aislar los servidores front-end de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red está inundada de tráfico externo no válido en un ataque de este tipo, el tráfico finaliza en el Director.

- **System Center Se recomienda Operations Manager.** Se recomienda supervisar el estado de la implementación Skype Empresarial Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede usar el System Center Operations Manager Management Pack para Skype Empresarial que está disponible como descarga gratuita de Microsoft. Con el módulo de administración de Skype Empresarial, puede obtener de forma proactiva alertas en tiempo real cuando se produzcan problemas, ejecutar transacciones sintéticas para probar la funcionalidad Skype Empresarial de un extremo a otro, obtener informes de disponibilidad del servicio, entre otros. Esto le ayuda a responder proactivamente a los problemas de la implementación antes de que los usuarios finales los experimenten.

## <a name="reference-topology-for-a-large-organization"></a>Topología de referencia para una organización grande

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el Sitio central A, 20 000 en el Sitio central B y un total de 10 000 en el Sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con un número cualquiera de usuarios.

Además de la alta disponibilidad proporcionada por los grupos de servidores front-end, esta topología agrega compatibilidad con la recuperación ante desastres. Los grupos de servidores front-end de los sitios centrales A y B se emparejan entre sí. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá pasar los servicios para los usuarios afectados al grupo emparejado en el sitio no afectado.

Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.

**Información general de la topología de referencia para organizaciones de gran tamaño con varios centros de datos**

![Topología de referencia para varios centros de datos.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central A**

![Topología 3-2.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central B**

![Topología 3-3.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topología de referencia para organizaciones de gran tamaño: Vista detallada del Sitio central C**

![Topología 3-4.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Los grupos de servidores front-end se emparejan para habilitar la recuperación ante desastres.** Los grupos de servidores front-end del sitio A y el sitio B se emparejan entre sí para proporcionar soporte técnico de recuperación ante desastres. Si se produce un error en el grupo de servidores de un sitio, el administrador puede conmutar por error a los usuarios de ese sitio al grupo front-end emparejado en el otro sitio, con un mínimo de interrupción del servicio para los usuarios. Cada uno de estos dos grupos de servidores front-end tiene seis servidores, suficiente para 40 000 usuarios en ambos grupos en caso de conmutación por error. Para obtener más información, vea [Plan for high availability and disaster recovery in Skype Empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Los servidores back-end se reflejan** Para proporcionar más alta disponibilidad para las características básicas del usuario, la organización ha implementado un par reflejado de servidores back-end para cada grupo de servidores front-end. Se trata de una topología opcional y podría elegir implementar un solo servidor back-end en su lugar. SQL clústeres y grupos de disponibilidad AlwaysOn también son compatibles. Para obtener más información, [vea Back End Server high availability in Skype Empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Usar Standard Edition servidor en un sitio de sucursal.** Esta organización considera el Sitio C como un sitio de sucursal porque solo tiene 600 empleados. Sin embargo, los usuarios de este sitio realizan muchas conferencias de A/V entre ellos. Si se implementó en Skype Empresarial Server como un sitio de sucursal, los medios para estas conferencias se ejecutarían a través de la red de área extensa (WAN) hacia y desde un sitio central que tenga implementado un servidor front-end. Para evitar esta posible carga de ancho de banda, han instalado un par de servidores Standard Edition en este sitio, que hospedará estas conferencias. Y como Standard Edition los servidores están instalados allí, Skype Empresarial Server por definición lo considera un sitio central y se trata como tal en el Generador de topologías y la herramienta de planeación.

    Solo un servidor Standard Edition sería suficiente para el rendimiento aquí, pero la organización ha implementado dos y los ha emparejado para proporcionar alta disponibilidad en caso de que un servidor se desalome.

    A pesar de que el Sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el Sitio C usará los servidores perimetrales implementados en el Sitio A.

- **Supervisión y archivado** Esta organización ha implementado tanto la supervisión como el archivado. Si se implementa Supervisión o Archivado, se ejecutará en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el Sitio central B. Las bases de datos de esta ubicación reciben datos de Supervisión y Archivado desde los servidores front-end de todos los sitios.

- **Opciones de implementación en sitios de sucursal.** En realidad, esta organización tiene más de 50 sitios de sucursal, de los que solo se muestran dos en los diagramas detallados. El sitio de sucursal 1 no tiene un vínculo WAN resistente al sitio central, por lo que tienen dispositivos de sucursal con funciones de supervivencia implementados para proporcionar servicio telefónico en caso de que el vínculo WAN al sitio central se desvanee. Sin embargo, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo necesita una puerta de enlace de red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite el desvío de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para obtener más información sobre cómo decidir qué instalar en un sitio de sucursal, vea [Plan for Telefonía IP empresarial resiliency in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Enlace troncal SIP y servidor de mediación.** Observe que en el Sitio central B, el servidor de mediación no está instalado con los servidores front-end. Esto se debe a que el servidor de mediación independiente es recomendable para sitios que usen el enlace troncal SIP. En la mayoría de casos restantes, se recomienda instalar el servidor de mediación con el servidor front-end. Para obtener más información sobre las topologías de servidor de mediación, consulte [Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server) en la documentación sobre planeamiento.

- **Chat persistente implementado.** Esta organización ha implementado los servidores necesarios para habilitar Chat persistente. Ha implementado varios servidores front-end de Chat persistente para, por un lado, procesar la carga del número de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado Cumplimiento para Chat persistente y ha ubicado el Almacén de Chat persistente y el Almacén de Cumplimiento de Chat persistente en servidores aparte. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.

    > [!NOTE]
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015.

- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales usan el equilibrio de carga dns. De esta forma, no son necesarios equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que se debe invertir en la configuración y el mantenimiento de los equilibradores de carga de hardware para el resto de grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener más información, vea (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implementación de mensajería unificada de Exchange.** Skype Empresarial Server funciona con implementaciones locales de Exchange mensajería unificada (MU) y la mensajería unificada hospedada Exchange mensajería unificada. El sitio central A incluye un Exchange de mensajería unificada (MU), que se ejecuta Microsoft Exchange Server, no Skype Empresarial Server. La Exchange de mensajería unificada para Skype Empresarial Server se ejecuta en el grupo de servidores front-end.

    El Sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas.

    Para obtener más información Exchange mensajería unificada, consulte [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) and [Hosted Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration) en la documentación sobre planeación.

- **Office Web Apps Server.** Se recomienda implementar un Office Web Apps Server o granja de servidores de Office Web Apps Server en cada organización que use conferencias web. Puede implementar una única granja de servidores de Office Web Apps Server en un sitio que sirva tráfico desde todos los sitios, o bien implementarla en cada sitio. Office Web Apps Server permite presentar diapositivas de PowerPoint en conferencias web.

- **Pueden agregarse Directores.** Si esta organización deseara una mayor seguridad contra ataques por denegación de servicio, podría implementar también un grupo de servidores de Directores. Un director es un rol de servidor independiente y opcional en Skype Empresarial Server que no tiene cuentas de usuario principales ni proporciona servicios de presencia o conferencia. Actúa como un servidor interno del próximo salto al que un servidor perimetral enruta el tráfico SIP entrante destinado a servidores internos. El director autentica previamente las solicitudes entrantes y las redirige al servidor o grupo de servidores principal del usuario. La preautenticación en el Director permite omitir solicitudes de cuentas de usuario desconocidas en la implementación. Un director ayuda a aislar los servidores front-end de tráfico malintencionado, como ataques de denegación de servicio (DoS). Si la red está inundada de tráfico externo no válido en un ataque de este tipo, el tráfico finaliza en el Director.

- **System Center Se recomienda Operations Manager.** Se recomienda supervisar el estado de la implementación Skype Empresarial Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede usar el System Center Operations Manager Management Pack para Skype Empresarial que está disponible como descarga gratuita de Microsoft. Con el módulo de administración de Skype Empresarial, puede obtener de forma proactiva alertas en tiempo real cuando se produzcan problemas, ejecutar transacciones sintéticas para probar la funcionalidad Skype Empresarial de un extremo a otro, obtener informes de disponibilidad del servicio, entre otros. Esto le ayuda a responder proactivamente a los problemas de la implementación antes de que los usuarios finales los experimenten.