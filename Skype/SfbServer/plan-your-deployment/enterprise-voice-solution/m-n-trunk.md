---
title: Tronco de MN en Skype para Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 'Skype para Telefonía IP empresarial de Business Server admite Troncalización m: n entre el servidor de mediación y componentes como puertas de enlace PSTN, controladores de límite de sesión y IP-PBX.'
ms.openlocfilehash: 2f94bc0981a4fe1a171a02259db399b7cbaf6e48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mn-trunk-in-skype-for-business-server-2015"></a>Tronco M:N en Skype Empresarial Server 2015
 
Skype para Telefonía IP empresarial de Business Server admite Troncalización m: n entre el servidor de mediación y componentes como puertas de enlace PSTN, controladores de límite de sesión y IP-PBX.
  
Skype para Business Server admite una mayor flexibilidad en la definición de un tronco para propósitos de enrutamiento de llamada respecto a versiones anteriores. Un tronco es una asociación lógica entre un servidor de mediación y el número de puerto de escucha con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos de acceso a la misma puerta de enlace; un servidor de mediación puede tener varios troncos de acceso a puertas de enlace distintas; por el contrario, una puerta de enlace puede tener varios troncos de acceso a diferentes servidores de mediación.
  
Debe crear aún un tronco raíz siempre que utilice el generador de topología para activado una puerta de enlace a la topología. El número de puertas de enlace que puede administrar un servidor de mediación determinado depende de la capacidad de procesamiento del servidor durante las horas de disponibilidad. Si implementa un servidor de mediación en hardware que supera los requisitos mínimos de hardware para Skype para Business Server, como se describe en los [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), entonces la estimación de cuántas llamadas de derivación no activas un puede controlar el servidor de mediación de independiente es aproximadamente 1000 llamadas. Cuando se implementa en la reunión de hardware se espera realizar la transcodificación, pero seguir enrutando llamadas para varias puertas de enlace, incluso si las puertas de enlace no son compatibles con estas especificaciones, el servidor de mediación medios de derivación.
  
Al definir una ruta de llamada, especificar los troncos asociados a esa ruta, pero no especifica que los servidores de mediación están asociados con esa ruta. En su lugar, utilice el generador de topología para asociar los troncos con servidores de mediación. En otras palabras, enrutamiento determina que el tronco para utilizarlo en una llamada y, posteriormente, el servidor de mediación asociado con ese tronco se envía a la señalización de esa llamada.
  
El servidor de mediación puede implementarse como un conjunto; Este grupo puede dar en combinación con un grupo de servidores Front-End, o se puede implementar como un grupo independiente. Cuando un servidor de mediación se combina con un grupo de servidores Front-End, el tamaño del grupo puede ser como máximo 12 (el límite del tamaño del registro). Juntas, estas nuevas capacidades aumentan la confiabilidad y la flexibilidad de implementación para servidores de mediación, pero que requieren capacidades de asociados en las siguientes entidades del mismo nivel:
  
- **Puerta de enlace RTC.** Un Skype para puerta de enlace completo Business Server debe implementar con equilibrio de carga DNS, lo que permite una puerta de enlace de red (conmutada PSTN) completo de telefonía pública conmutada para que actúe como un equilibrador de carga para un grupo de servidores de mediación y, por tanto, para equilibrar la carga de llamadas en todo el repositorio .
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del conjunto de servidor de mediación para el SBC, el SBC puede recibir conexiones desde cualquier servidor de mediación en el grupo. En la dirección de la CE a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación en el grupo. Esto puede conseguirse a través del equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa consiste en dar al proveedor de servicios de las direcciones IP de todos los servidores de mediación en el grupo y el proveedor de servicios le proveerá estos en su SBC como tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios gestionará el equilibrio de carga para sus propios servidores. Es posible que no todos los proveedores de servicios o SBC admitan estas capacidades. Además, es posible que el proveedor de servicios exija cargos adicionales para esta capacidad. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección del conjunto de servidor de mediación para la terminación SIP IP-PBX, IP-PBX puede recibir conexiones desde cualquier servidor de mediación en el grupo. En la dirección de IP-PBX a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación en el grupo. Porque la mayoría de IP-PBX no admiten equilibrio de carga DNS, se recomienda definir conexiones SIP directas individuales desde IP-PBX para cada servidor de mediación en el grupo. La IP-PBX gestionará su propio equilibrio de carga al distribuir el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en la IP-PBX. Si una determinada IP-PBX admite este concepto de grupo troncal y cómo se intersecta con la redundancia del IP-PBX propio y arquitectura de clustering debe determinarse antes de que usted puede decidir si un clúster de servidor de mediación puede interactuar correctamente con un IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con el que interactúa. Esto significa que todos los miembros del grupo obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por tanto, no hay ninguna forma de segmentar el grupo para que algunos servidores de mediación comunicarse con sólo ciertos pares de puerta de enlace para las llamadas salientes. Si es necesaria la segmentación de este tipo, debe utilizarse un conjunto independiente de servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, los troncos SIP o las IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo, tal y como se ha explicado anteriormente en este mismo tema.
  
Una puerta de enlace PSTN determinado, IP-PBX o interlocutor de troncal SIP puede enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que puede controlar un determinado grupo de servidores de mediación depende del número de llamadas que utilizan la omisión de medios. Si un gran número de llamadas utilice la omisión de medios, un servidor de mediación en el grupo puede controlar muchas más llamadas, porque sólo señalización capa es necesario. 
  

