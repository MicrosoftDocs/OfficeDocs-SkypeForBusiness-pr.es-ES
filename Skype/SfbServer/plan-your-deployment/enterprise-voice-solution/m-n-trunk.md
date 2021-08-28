---
title: Tronco MN en Skype Empresarial Server
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype Empresarial Server Telefonía IP empresarial admite el enlace troncal M:N entre el servidor de mediación y componentes como puertas de enlace RTC, controladores de borde de sesión e IP-PBX.
ms.openlocfilehash: 6c63c01609e35be014aae9c3019c8f96c9b95b41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601345"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Tronco M:N en Skype Empresarial Server
 
Skype Empresarial Server Telefonía IP empresarial admite el enlace troncal M:N entre el servidor de mediación y componentes como puertas de enlace RTC, controladores de borde de sesión e IP-PBX.
  
Skype Empresarial Server mayor flexibilidad en la definición de un tronco para fines de enrutamiento de llamadas de versiones anteriores. Un tronco es una asociación lógica entre un servidor de mediación y un número de puerto de escucha con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos en la misma puerta de enlace; un servidor de mediación puede tener varios troncos a puertas de enlace diferentes; Por el contrario, una puerta de enlace puede tener varios troncos a distintos servidores de mediación.
  
Debe crear un tronco raíz siempre que use el Generador de topologías para agregar una puerta de enlace a la topología. El número de puertas de enlace que un servidor de mediación determinado puede controlar depende de la capacidad de procesamiento del servidor durante las horas de mayor actividad. Si implementa un servidor de mediación en hardware que supera los requisitos mínimos de hardware para Skype Empresarial Server, tal como se describe en Requisitos de servidor para [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), la estimación de cuántas llamadas activas sin omisión puede controlar un servidor de mediación independiente es de aproximadamente 1000 llamadas. Cuando se implementa en hardware que reúne estas especificaciones, se espera que el servidor de mediación realice la transcodificación, pero sigue enrutando las llamadas de varias puertas de enlace incluso si las puertas de enlace no admiten la omisión de medios.
  
Al definir una ruta de llamada, se especifican los troncos asociados a esa ruta, pero no se especifica qué servidores de mediación están asociados a esa ruta. En su lugar, se usa el Generador de topologías para asociar troncos con servidores de mediación. En otras palabras, el enrutamiento determina qué tronco usar para una llamada y, posteriormente, el servidor de mediación asociado a ese tronco se envía la señalización de esa llamada.
  
El servidor de mediación se puede implementar como un grupo de servidores; este grupo puede colocarse con un grupo de servidores front-end o puede implementarse como un grupo independiente. Cuando un servidor de mediación se asocia con un grupo de servidores front-end, el tamaño del grupo puede ser como máximo 12 (el límite del tamaño del grupo de registradores). En conjunto, estas nuevas capacidades aumentan la confiabilidad y la flexibilidad de implementación para los servidores de mediación, pero requieren funcionalidades asociadas en las siguientes entidades del mismo nivel:
  
- **Puerta de enlace RTC.** Una puerta de enlace calificada de Skype Empresarial Server debe implementar el equilibrio de carga dns, lo que permite que una puerta de enlace de red telefónica conmutada (RTC) calificada actúe como equilibrador de carga para un grupo de servidores de mediación y, por lo tanto, equilibrar la carga de las llamadas en todo el grupo.
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación al SBC, el SBC puede recibir conexiones desde cualquier servidor de mediación del grupo. En la dirección del SBC al grupo de servidores, el tráfico se puede enviar a cualquier servidor de mediación del grupo. Esto puede conseguirse mediante el equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa es proporcionar al proveedor de servicios las direcciones IP de todos los servidores de mediación del grupo y el proveedor de servicios las aprovisionará en su SBC como un tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios administrará el equilibrio de carga para sus propios servidores. No todos los proveedores de servicios y SBC admiten estas capacidades. Además, es posible que el proveedor de servicios exija costos adicionales. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección desde el grupo de servidores de mediación hasta la terminación SIP IP-PBX, la IP-PBX puede recibir conexiones desde cualquier servidor de mediación del grupo. En la dirección desde la IP-PBX al grupo de servidores, el tráfico se puede enviar a cualquier servidor de mediación del grupo. Dado que IP-PBXs no admiten el equilibrio de carga dns, se recomienda definir conexiones SIP directas individuales desde la IP-PBX a cada servidor de mediación del grupo. El sistema IP-PBX administrará su propio equilibrio de carga distribuyendo el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en el sistema IP-PBX. Debe determinarse si una IP-PBX determinada admite este concepto de grupo troncal y cómo se cruza con la propia arquitectura de agrupación y redundancia de IP-PBX antes de decidir si un clúster de servidor de mediación puede interactuar correctamente con una IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con la que interactúa. Esto significa que todos los miembros del grupo de servidores obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay forma de segmentar el grupo de modo que algunos servidores de mediación se comuniquen con solo determinados pares de puerta de enlace para las llamadas salientes. Si dicha segmentación es necesaria, debe usarse un grupo independiente de servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, troncos SIP o sistemas IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo de servidores, tal y como se ha explicado anteriormente en este mismo tema.
  
Una puerta de enlace RTC determinada, IP-PBX o el mismo nivel troncal SIP pueden enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que puede controlar un grupo determinado de servidores de mediación depende del número de llamadas que usan la omisión de medios. Si un gran número de llamadas usan desvío de medios, un servidor de mediación del grupo de servidores puede controlar muchas más llamadas, ya que solo es necesario procesar la capa de señalización. 
  

