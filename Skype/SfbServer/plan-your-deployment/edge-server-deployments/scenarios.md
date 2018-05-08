---
title: Escenarios del servidor perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Resumen: Revise estos escenarios para ayudarle a planear la topología de servidor perimetral de Skype para Business Server 2015.'
ms.openlocfilehash: 9afe23c626f2a266061c250740e52bc55dd2697d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="edge-server-scenarios-in-skype-for-business-server-2015"></a>Escenarios del servidor perimetral en Skype Empresarial Server 2015
 
**Resumen:** Revise estos escenarios para ayudarle a planear la topología de servidor perimetral de Skype para Business Server 2015.
  
Tenemos algunos diagramas de escenarios para ayudar a visualizar y decidir en qué Skype para la topología de servidor perimetral de Business Server que desee implementar. Una vez que haya seleccionado un buen candidato, puede leer los requisitos del entorno que tendrá que abordar. Lo siguiente se aplica a cualquiera de los escenarios, por lo que lo mencionamos primero.
  
Estas ilustraciones, que se muestran solo con fines de ejemplo (y como tal contienen ejemplos de datos de IPv4 e IPv6), no representan el flujo de comunicación real, sino una vista de alto nivel de su posible tráfico. También se puede ver información de los puertos en los Diagramas de puertos para cada escenario que se muestra a continuación.
  
Los diagramas muestran .com para la interfaz externa y .net para la interna, que también es material de muestra. Por supuesto, sus propias entradas pueden ser muy diferentes cuando esté elaborando su propio plan perimetral final.
  
No incluimos el Director (que es un componente opcional) en cualquiera de los diagramas, pero puede leer sobre que por separado (se menciona en otros temas de planeación).
  
Como se indica anteriormente, hay datos de ejemplo de IPv6 en los diagramas. La mayor parte de la documentación de [planeación para las implementaciones de servidor perimetral de Skype para Business Server 2015](edge-server-deployments.md) se hará referencia a IPv4, pero sin duda son compatibles si va a usar IPv6. Tenga en cuenta que necesitará direcciones IPv6 en el espacio de direcciones asignadas y que tendrán que funcionar con el direccionamiento interno y el externo, al igual que con IP de IPv4. Puede, con Windows, recurrir a la característica de pila doble, que es una pila de red diferente y separada para IPv4 e IPv6. Esto permitirá, si lo necesita, asignar las direcciones IPv4 e IPv6 simultáneamente.
  
Hay dispositivos NAT que permiten para NAT64 (IPv6 a IPv4) y NAT66 (IPv6 a IPv6)), y esto es válido para su uso con Skype para Business Server.
  
> [!IMPORTANT]
> Si está usando el servicio de control de admisión de llamadas (CAC), tiene que usar IPv4 en la interfaz interna para que funcione. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Consolidado de único Skype para servidor perimetral de Business Server privada de direcciones IP y NAT

Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significa que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es una necesidad, compruebe los escenarios consolidados ampliados a continuación.
  
![Escenario perimetral para el perímetro consolidado único con IP privada por medio de NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puerto

También tenemos un diagrama para los puertos para un solo los servidores perimetrales consolidados.
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Consolidado de único Skype para servidor perimetral de Business Server con direcciones IP públicas

Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significa que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es una necesidad, compruebe los escenarios consolidados ampliados a continuación.
  
![Escenario perimetral para el perímetro consolidado único con IP pública](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puerto

También tenemos un diagrama para los puertos para un solo los servidores perimetrales consolidados.
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Carga de Skype consolidada escalada para el grupo de negocio de servidor perimetral, con DNS equilibrio y privada de direcciones IP y de NAT

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le proporciona las ventajas de escalabilidad y compatibilidad con la conmutación por error.
  
![Escenario perimetral para el perímetro consolidado escalado, equilibrador de carga de DNS con IP privada por medio de NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puerto

También tenemos un diagrama para grupos de servidores de perimetral consolidadas escaladas con equilibrio de carga DNS.
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral con equilibrador de carga de DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Direcciones IP públicas y equilibrio de carga de Skype consolidada escalada para el grupo de negocio de servidor perimetral, con DNS

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le proporciona las ventajas de escalabilidad y compatibilidad con la conmutación por error.
  
![Escenario perimetral para el perímetro consolidado escalado, equilibrador de carga de DNS con IP pública](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puerto

También tenemos un diagrama para grupos de servidores de perimetral consolidadas escaladas con equilibrio de carga DNS.
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral con equilibrador de carga de DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Escalada consolidada Skype para grupo de negocio de servidor perimetral, con equilibrio de carga de hardware

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le proporciona las ventajas de escalabilidad y compatibilidad con la conmutación por error.
  
![Escenario perimetral para el perímetro consolidado escalado con equilibrador de carga de hardware](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>Diagrama de puerto

También tenemos un diagrama para escalada consolidadas grupos de servidores perimetrales con equilibrio de carga de hardware
  
![Protocolos y puertos de la red perimetral de servidores perimetrales](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

