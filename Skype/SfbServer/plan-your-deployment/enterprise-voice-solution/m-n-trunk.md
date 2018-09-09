---
title: Tronco MN en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 'Skype para Business Server Enterprise Voice admite conexiones basadas en troncos de m: n entre el servidor de mediación y componentes, como las puertas de enlace RTC, controladores de borde de sesión y IP-PBX.'
ms.openlocfilehash: 548ba95d3cd3b8c21fcb5fb489f5c70e70a80ce2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882175"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Tronco m: n en Skype para Business Server
 
Skype para Business Server Enterprise Voice admite conexiones basadas en troncos de m: n entre el servidor de mediación y componentes, como las puertas de enlace RTC, controladores de borde de sesión y IP-PBX.
  
Skype para Business Server admite mayor flexibilidad en la definición de un tronco para fines de enrutamiento de llamadas desde versiones anteriores. Un tronco es una asociación entre un servidor de mediación y el número de puerto de escucha lógica con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos de acceso a la misma puerta de enlace; un servidor de mediación puede tener varios troncos de acceso a distintas puertas de enlace; por el contrario, una puerta de enlace puede tener varios troncos a diferentes servidores de mediación.
  
Debe crear aún un tronco raíz siempre que use el generador de topología para activado una puerta de enlace a la topología. El número de puertas de enlace que puede administrar un servidor de mediación determinado depende de la capacidad de procesamiento del servidor durante las horas de disponibilidad. Si implementa un servidor de mediación en hardware que supere los requisitos de hardware mínimos de Skype para Business Server, tal como se describe en [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), a continuación, la estimación de cuántas llamadas sin desvío activas un puede controlar el servidor de mediación independiente es aproximadamente 1000 llamadas. Cuando se implementa en la reunión de hardware estas especificaciones, el servidor de mediación se prevé realizar transcodificación, pero aún enrutar las llamadas para varias puertas de enlace incluso si las puertas de enlace no admiten el desvío de medios.
  
Al definir una ruta de llamada, especifique los troncos asociados con esa ruta, pero no se especifica que los servidores de mediación están asociados a esa ruta. En su lugar, use el generador de topología para asociar troncos con los servidores de mediación. En otras palabras, el enrutamiento determina qué tronco que se usará para una llamada y, posteriormente, se envía el servidor de mediación asociado con ese tronco la señalización de que la llamada.
  
El servidor de mediación puede implementarse como un grupo de servidores; Este grupo de servidores se puede combinar con un grupo de servidores Front-End, o se puede implementar como un grupo de servidores independiente. Cuando un servidor de mediación se combina con un grupo de servidores Front-End, el tamaño del grupo de servidores puede ser como máximo 12 (el límite del tamaño del grupo de servidores de registrador). Juntas, estas nuevas capacidades aumentan la confiabilidad y la flexibilidad de implementación para los servidores de mediación, pero que requieren capacidades de asociados en las siguientes entidades del mismo nivel:
  
- **Puerta de enlace RTC.** Un Skype para puerta de enlace completa Business Server debe implementar con equilibrio de carga DNS, lo que permite que una puerta de enlace de completa telefónica conmutada (RTC) para que actúen como un equilibrador de carga para un grupo de servidores de mediación y, desde allí, a las llamadas de equilibrar la carga entre el grupo de servidores .
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación a la SBC, los SBC puede recibir conexiones desde cualquier servidor de mediación del grupo de servidores. En la dirección de la SBC para el grupo de servidores, se puede enviar el tráfico a cualquier servidor de mediación del grupo de servidores. Esto puede conseguirse a través del equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa consiste en proporcionar al proveedor de servicios de las direcciones IP de todos los servidores de mediación en el grupo de servidores, y el proveedor de servicios se aprovisione estos en su SBC como un tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios gestionará el equilibrio de carga para sus propios servidores. Es posible que no todos los proveedores de servicios o SBC admitan estas capacidades. Además, es posible que el proveedor de servicios exija cargos adicionales para esta capacidad. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección del grupo de servidores de mediación para la terminación de SIP de IP-PBX, IP-PBX puede recibir conexiones desde cualquier servidor de mediación del grupo de servidores. En la dirección de la IP-PBX para el grupo de servidores, se puede enviar el tráfico a cualquier servidor de mediación del grupo de servidores. Debido a que la mayoría de las PBX IP no admiten el equilibrio de carga DNS, se recomienda que se defina individuales conexiones SIP directas desde el IP-PBX para cada servidor de mediación del grupo de servidores. La IP-PBX gestionará su propio equilibrio de carga al distribuir el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en la IP-PBX. Si un determinado sistema IP-PBX admite este concepto de grupo de tronco y cómo cruza con la redundancia del IP-PBX propio y agrupación en clústeres de arquitectura debe determinarse antes de que puede decidir si un clúster de servidor de mediación puede interactuar correctamente con un IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace de mismo nivel con el que interactúa. Esto significa que todos los miembros del grupo obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay ninguna forma para segmentar el grupo de servidores para que algunos servidores de mediación comunicarse con sólo ciertos interlocutores de puerta de enlace para las llamadas salientes. Si la segmentación de este tipo es necesaria, se debe usar un grupo de servidores independiente de los servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, los troncos SIP o las IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo, tal y como se ha explicado anteriormente en este mismo tema.
  
Una determinada puerta de enlace de RTC, IP-PBX o punto de tronco SIP puede enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que puede controlar un determinado grupo de servidores de mediación depende del número de llamadas que usan el desvío de medios. Si un gran número de llamadas usa el desvío de medios, un servidor de mediación del grupo de servidores pueden controlar muchas más llamadas, debido a que el procesamiento de capa de señalización sólo es necesario. 
  

