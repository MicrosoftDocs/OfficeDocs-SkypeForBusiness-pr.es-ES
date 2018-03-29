---
title: Topologías de referencia para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologías de referencia para Skype para Business Server, incluidos diagramas y decisiones que debe tomar grandes y medianas y las organizaciones pequeñas.
ms.openlocfilehash: 5019e292344dfe20ee086ff6ceb86c11aeeee944
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="reference-topologies-for-skype-for-business-server-2015"></a>Topologías de referencia para Skype Empresarial Server 2015
 
Topologías de referencia para Skype para Business Server, incluidos diagramas y decisiones que debe tomar grandes y medianas y las organizaciones pequeñas.
  
El mejor Skype para la topología de servidores de negocios para usted depende del tamaño de su organización, las cargas de trabajo que va a implementar y las preferencias para una alta disponibilidad en comparación con el costo de la inversión. 
  
En esta sección se describen tres topologías de referencia de ejemplo, además de la lógica que impera en muchas de las decisiones que determinan cada topología.
  
## <a name="reference-topology-for-a-small-organization"></a>Topología de referencia para una organización pequeña

La topología de referencia para las organizaciones pequeñas, muestra cómo puede implementar una solución sólida y de alta disponibilidad mediante la implementación de sólo tres servidores que ejecutan Skype para Business Server.
  
**Topología de referencia para las organizaciones pequeñas**

![Diagrama de la topología de referencia con tres servidores implementados](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)
  
- **Par de servidores Standard Edition implementados** Esta organización tiene 4000 usuarios en su sitio central. Han implementado dos servidores Standard Edition y emparejados juntos para habilitar alta disponibilidad y recuperación ante desastres. Cada usuarios de casas 2.000 server, pero la información acerca de todos los usuarios se sincronizan entre los dos servidores. Si uno falla, un administrador puede conmutar a esos usuarios para ser servido por el servidor, con un mínimo de interrupción para los usuarios. Para obtener más información acerca de la alta disponibilidad y funciones de recuperación de desastres de Skype para Business Server, consulte el [Plan para alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
- **Recomendamos la implementación de un servidor perimetral.** Aunque no es necesaria la implementación de un servidor perimetral para la mensajería instantánea (MI), la presencia y la conferencia, recomendamos efectuarla incluso en el caso de implementaciones pequeñas. Puede maximizar su Skype para inversión Business Server mediante la implementación de un servidor perimetral para proporcionar servicio a los usuarios actualmente fuera de los servidores de seguridad de su organización. Entre las ventajas se incluye las siguientes:
    
  - Los usuarios de la organización pueden utilizar Skype para la funcionalidad de servidor de la empresa, si está trabajando desde casa o está fuera de la carretera.
    
  - Los usuarios pueden invitar a usuarios externos para participar en reuniones.
    
  - Si tienes un socio, el proveedor o la organización del cliente que también utiliza Skype para Business Server, pueden formar una relación con esa organización federada. Su Skype para la implementación de Business Server detectará a los usuarios de dicha organización federada, lleva a una mejor colaboración.
    
  - Los usuarios pueden intercambiar mensajes instantáneos con usuarios de algunos servicios de mensajería instantánea (MI) pública.
    
- **Supervivencia de sitios de sucursal.** Esta organización está ejecutando un programa piloto de la característica de Telefonía IP empresarial de Skype para Business Server. Algunos usuarios utilizan Skype para Business Server como su solución de voz único. Algunos de estos usuarios piloto de Telefonía IP empresarial se encuentran en el sitio de sucursal. El sitio de la sucursal no tiene un vínculo de confiable de área extensa (WAN) para el sitio central, para que un dispositivo de la rama que sobreviven desplegado en ella. Gracias a esta implementación, si el vínculo WAN deja de funcionar, los usuarios del sitio de sucursal podrán seguir realizando y recibiendo llamadas (llamadas dentro de la organización y llamadas RTC), disponer de la función del correo de voz y comunicarse por medio de la mensajería instantánea (MI) entre dos participantes. Los usuarios también pueden autenticarse cuando el vínculo WAN no está disponible. Para obtener más información, vea [Planear resistencia de Telefonía IP empresarial en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de Exchange Unified Messaging (UM), que se ejecuta Microsoft Exchange Server, no Skype para Business Server.
    
- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.
    
## <a name="reference-topology-for-a-medium-organization"></a>Topología de referencia para una organización mediana

La topología de referencia con alta disponibilidad y un único centro de datos está diseñada para pequeñas y medianas organizaciones con un sitio central. La topología exacta del diagrama siguiente es para una organización de 20 000 usuarios. 
  
**Topología de referencia para las organizaciones medianas**

![Diagrama de la topología de referencia para un solo centro de datos](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)
  
- **Incluya más usuarios al agregar más servidores front-end.** La topología exacta de este diagrama tiene tres servidores front-end para proporcionar compatibilidad para 20 000 usuarios. Si dispone de un único sitio central y más usuarios, solo tiene que agregar más servidores front-end al grupo de servidores. La cantidad máxima de usuarios por grupo de servidores es de 80 000, con doce servidores front-end.
    
    Pero, la topología de sitio único puede admitir incluso más usuarios si se agrega otro grupo de servidores front-end al sitio. 
    
- **Es posible agregar la recuperación ante desastres.** Para esta organización, alta disponibilidad para su Skype para servicios Business Server es una característica necesaria, pero no es de recuperación ante desastres. El grupo de servidores frontales han implementado proporciona alta disponibilidad.
    
    Si desearan agregar la capacidad de recuperación ante desastres, podrían pensar en establecer otro centro de datos y agregar allí otro grupo de servidores front-end y vincularlo con el grupo de servidores front-end de su centro de datos actual. Luego, si se produjera un desastre que afectara al grupo principal, los administradores podrían realizar la conmutación por error de los usuarios al grupo de copia de seguridad.
    
- **Servidores de fondo atrás están reflejados** Para proporcionar la más alta disponibilidad para funciones de usuario básica, la organización ha implementado un par espejeado detrás de servidores de fondo para cada grupo de servidores Front-End.
    
- **Opciones de bases de datos del servidor de supervisión.** Esta organización ha implementado la supervisión para garantizar la calidad de las llamadas de Telefonía IP empresarial y A / conferencias. La supervisión se implementa en cada servidor front-end y la base de datos de supervisión se combina con los servidores back-end. También se admiten topologías en las que la base de datos de supervisión se encuentra en un servidor independiente.
    
- **Alta disponibilidad del servidor de borde** En esta organización de ejemplo con 20.000 usuarios, sería suficiente para obtener un rendimiento un solo servidor perimetral. Pero, se ha implementado un grupo de dos servidores perimetrales para proporcionar alta disponibilidad.
    
- **Opciones de implementación de sitios de sucursal.** La organización en esta topología tiene Telefonía IP empresarial implementado como su solución de voz. Sitio de sucursal 1 no tiene un vínculo de resistente de área extensa (WAN) con el sitio central, por lo que tiene un dispositivo de sucursal que sobreviven implementado para mantener que muchos Skype para las características de Business Server en caso de que el vínculo WAN con el sitio central deja de funcionar. Pero, el sitio de sucursal 2 tiene un vínculo WAN resistente, por lo que solo se necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada allí permite la omisión de medios, por lo que no se necesita ningún servidor de mediación en el sitio de sucursal 2. Para obtener más información, vea [Planear resistencia de Telefonía IP empresarial en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales tienen implementado el equilibrio de carga de DNS para el tráfico SIP. Este equilibrio elimina la necesidad de equilibradores de carga de hardware para los servidores perimetrales y reduce notablemente la instalación y el mantenimiento de los equilibradores de carga de hardware de otros grupos de servidores, ya que estos equilibradores solo se necesitan para tráfico HTTP. Para obtener más información, vea (.. /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).
    
- **Implementación de mensajería unificada de Exchange.** Esta topología de referencia incluye un servidor de Exchange Unified Messaging (UM), que se ejecuta Microsoft Exchange Server, no Skype para Business Server.
    
- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web.
    
- **Es posible agregar directores.** Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un Director es un rol de servidor independiente, opcional en Skype para Business Server que no cuentas de usuario de inicio, o proporcionar servicios de presencia o conferencia. Actúa como un servidor interno de salto siguiente al que un servidor perimetral enruta el tráfico SIP entrante destinado a servidores internos. El Director autentica previamente las solicitudes entrantes y las redirige al usuario particular o grupo de servidores. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un Director ayuda a aislar los servidores frontales de tráfico malintencionado, como los ataques de denegación de servicio (DoS). Si la red está desborda por el tráfico externo no válido en este tipo de ataque, el tráfico se termina en el Director.
    
- **Se recomienda System Center Operations Manager.** Se recomienda que supervise el estado de su Skype para la implementación de Business Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede utilizar System Center Operations Manager Management Pack para Skype para el negocio que está disponible como una descarga gratuita de Microsoft. Con Skype para el módulo de administración de negocios, puede obtener de forma activa alertas en tiempo real cuando se producen problemas, ejecutar transacciones sintéticas para probar Skype end-to-end para la funcionalidad empresarial, obtener informes de disponibilidad del servicio y así sucesivamente. Esto le ayudará a responder de manera proactiva a problemas con su implementación antes de que los usuarios finales experimentan ellos.
    
## <a name="reference-topology-for-a-large-organization"></a>Topología de referencia para una organización de gran tamaño

La topología de referencia para una organización de gran tamaño con varios centros de datos es compatible con organizaciones de cualquier tamaño con más de un sitio central. La topología exacta del diagrama siguiente es para una organización de 50 000 usuarios, con 20 000 usuarios en el sitio central A, 20 000 en el sitio central B y un total de 10 000 en el sitio central C y los sitios de sucursal. El tipo de topología mostrada en este diagrama puede adaptarse a organizaciones con cualquier cantidad de usuarios.
  
Además de la alta disponibilidad que ofrece por pools de servidores frontales, esta topología agrega soporte para recuperación ante desastres. Los grupos de Front-End en las sedes centrales A y B están emparejados. Si uno de estos grupos de servidores deja de funcionar, el administrador podrá cambiar los servicios de los usuarios afectados al grupo emparejado en el sitio no afectado.
  
Esta topología se muestra en varios diagramas con información general seguida de vistas detalladas de los sitios centrales.
  
**Resumen de la topología de referencia para las grandes organizaciones con datos de varios centros**

![Topología de referencia para varios centros de datos](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)
  
**Topología de referencia para las grandes organizaciones: detalle de un sitio Central**

![Topología 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)
  
**Topología de referencia para las grandes organizaciones: detalle de b. Central**

![Topología 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)
  
**Topología de referencia para las grandes organizaciones: detalle de C de sitio Central**

![Topología 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)
  
- **Grupos de extremo frontales están emparejados para habilitar la recuperación ante desastres.** Los grupos de Front-End en el sitio A y el sitio B se emparejan entre sí, para proporcionar soporte para recuperación ante desastres. Si se produce un error en el grupo en un sitio, el administrador puede conmutar a los usuarios de ese sitio a la agrupación de Front-End emparejado en el sitio, con un mínimo de interrupción del servicio para los usuarios. Cada uno de estos dos grupos de servidores front-end tiene seis servidores, suficiente para 40 000 usuarios en ambos grupos en caso de la conmutación por error. Para obtener más información, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
    
- **Servidores de fondo atrás están reflejados** Para proporcionar la más alta disponibilidad para funciones de usuario básica, la organización ha implementado un par espejeado detrás de servidores de fondo para cada grupo de servidores Front-End. Ésta es una topología opcional y se puede implementar un único servidor de final de nuevo en su lugar. SQL clustering y los grupos de disponibilidad AlwaysOn también son compatibles. Para obtener más información, vea el [nuevo servidor de alta disponibilidad en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
    
- **Utilizando el servidor Standard Edition en un sitio de sucursal.** Esta organización considera C del sitio como un sitio de sucursal porque tiene sólo 600 empleados. Sin embargo, los usuarios tienen multitud / conferencias entre sí. Si se implementó en Skype para Business Server como un sitio de sucursal, se ejecutaría el medio para estas conferencias a través de la red de área extensa (WAN) hacia y desde un sitio central que tiene un servidor Front-End implementado. Para evitar esta carga potencial de ancho de banda, ha instalado a un par de servidores Standard Edition en este sitio, que albergará estas conferencias. Y dado que están instalados los servidores Standard Edition, Skype para Business Server por definición considera un sitio central y se trata como tal en el generador de topología y la herramienta de planeación.
    
    Un solo servidor Standard Edition sería suficiente para rendimiento aquí, pero la organización ha implementado dos y emparejados juntos para proporcionar alta disponibilidad en caso de que un servidor deja de funcionar.
    
    A pesar de que el sitio C se considera un sitio central, no es necesario implementar servidores perimetrales en él. En este ejemplo, el sitio C usará los servidores perimetrales implementados en el sitio A.
    
- **Monitoreo y Archiving** Esta organización ha implementado supervisión y archivado. Si se implementa la supervisión o el archivado, se ejecutarán en todos los servidores front-end. Las bases de datos de estas características pueden combinarse con la base de datos back-end, o bien ubicarse en un servidor aparte. Esta organización ha ubicado dichas bases de datos en un servidor aparte de los servidores back-end, en el sitio central B. Las bases de datos de esta ubicación reciben datos de supervisión y archivado desde los servidores front-end de todos los sitios.
    
- **Opciones de implementación en sitios de sucursal.** Esta organización tiene en realidad más de 50 sitios de sucursal y, en los diagramas detallados, solo se muestran dos de ellos. Sitio de sucursal 1 no tiene una WAN resistente vincular al sitio central, por lo que tienen que sobreviven de rama de dispositivos implementado para proporcionar servicio telefónico en caso de que el vínculo WAN con el sitio central deja de funcionar. Pero, el sitio de sucursal 2 sí tiene un vínculo WAN resistente, de modo que solo necesita una puerta de enlace de la red telefónica conmutada (RTC). La puerta de enlace RTC implementada en este caso admite la omisión de medios, por lo que en el sitio de sucursal 2 no es necesario ningún servidor de mediación. Para obtener más información acerca de cómo decidir lo que desea instalar en un sitio de sucursal, consulte [Plan de resiliencia de Telefonía IP empresarial en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).
    
- **Troncalización SIP y servidor de mediación.** Observe que en el sitio Central de B, servidor de mediación no se combina con los servidores frontales. Esto es porque el servidor de mediación de independiente se recomienda para sitios que utilizan SIP trunking. En la mayoría de los demás casos, se recomienda que colocar el servidor de mediación con el servidor Front-End. Para obtener más información acerca de las topologías de servidor de mediación, vea [componentes y topologías de servidor de mediación](http://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) en la documentación de planeamiento.
    
- **Chat persistente implementado.** Esta organización ha implementado los servidores necesarios para habilitar el chat persistente. Ha implementado varios servidores front-end de chat persistente para, por un lado, procesar la carga de la cantidad de usuarios del grupo de servidores y, por otro, ofrecer alta disponibilidad. También ha implementado el cumplimiento para el chat persistente y ha ubicado el almacén de chat persistente y el almacén de cumplimiento de chat persistente en servidores independientes. Estos almacenes pueden combinarse entre sí e incluso con el servidor back-end, pero esta organización ha optado por separarlos para ofrecer un mejor rendimiento.
    
- **Equilibrio de carga de DNS.** El grupo de servidores front-end y el grupo de servidores perimetrales utilizan el equilibrio de carga de DNS. De esta manera, no son necesarios los equilibradores de carga de hardware para la interfaz interna de los servidores perimetrales y se reduce significativamente la cantidad de tiempo que necesaria para la instalación y el mantenimiento de los equilibradores de carga de hardware para el resto de los grupos de servidores, ya que los equilibradores de carga de hardware solo se necesitan para el tráfico HTTP. Para obtener más información, vea (.. /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).
    
- **Implementación de mensajería unificada de Exchange.** Skype para Business Server funciona con las implementaciones locales de bothon de mensajería unificada de Exchange andhosted de Exchange Unified Messaging (UM). Sitio central A incluye un servidor de Exchange Unified Messaging (UM), que se ejecuta Microsoft Exchange Server, no Skype para Business Server. La funcionalidad de mensajería unificada de Exchange para Skype para Business Server se ejecuta en el grupo de servidores Front-End.
    
    El sitio central B usa servicios de Exchange hospedados, de modo que las funciones del servidor de mensajería unificada de Exchange también están hospedadas. 
    
    Para obtener más información acerca de la mensajería unificada de Exchange, consulte [Integración local Exchange Unified Messaging](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) y [Alojado Exchange integración de mensajería unificada](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) en la documentación de planeamiento.
    
- **Servidor de Office Web Apps.** Recomendamos implementar un servidor de Office Web Apps o una granja de servidores de Office Web Apps en cada organización que use conferencias web. Puede implementar una granja de servidor de Office Web Apps solo en un sitio que sirve el tráfico de todos los sitios, o implementarlo en cada sitio. El servidor de Office Web Apps permite presentar diapositivas de PowerPoint en conferencias web. 
    
- **Es posible agregar directores.** Si esta organización deseara aumentar la seguridad contra ataques por denegación de servicio, también podría implementar un grupo de directores. Un Director es un rol de servidor independiente, opcional en Skype para Business Server que no cuentas de usuario de inicio, o proporcionar servicios de presencia o conferencia. Actúa como un servidor interno de salto siguiente al que un servidor perimetral enruta el tráfico SIP entrante destinado a servidores internos. El Director autentica previamente las solicitudes entrantes y las redirige al usuario particular o grupo de servidores. La autenticación previa en el director permite quitar las solicitudes de cuentas de usuario desconocidas de la implementación. Un Director ayuda a aislar los servidores frontales de tráfico malintencionado, como los ataques de denegación de servicio (DoS). Si la red está desborda por el tráfico externo no válido en este tipo de ataque, el tráfico se termina en el Director.
    
- **Se recomienda System Center Operations Manager.** Se recomienda que supervise el estado de su Skype para la implementación de Business Server para ayudar a garantizar la disponibilidad del servicio para los usuarios finales. Puede utilizar System Center Operations Manager Management Pack para Skype para el negocio que está disponible como una descarga gratuita de Microsoft. Con Skype para el módulo de administración de negocios, puede obtener de forma activa alertas en tiempo real cuando se producen problemas, ejecutar transacciones sintéticas para probar Skype end-to-end para la funcionalidad empresarial, obtener informes de disponibilidad del servicio y así sucesivamente. Esto le ayudará a responder de manera proactiva a problemas con su implementación antes de que los usuarios finales experimentan ellos.
    

