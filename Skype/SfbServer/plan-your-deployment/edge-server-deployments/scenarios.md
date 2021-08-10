---
title: Escenarios de servidor perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Resumen: revise estos escenarios para ayudarle a planear la topología del servidor perimetral en Skype Empresarial Server.'
ms.openlocfilehash: df654740ae8b0fb6f7ce39669a14f3e7151220a24527166e996f1ceda583d2d7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306991"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Escenarios de servidor perimetral en Skype Empresarial Server
 
**Resumen:** Revise estos escenarios para ayudarle a planear la topología del servidor perimetral en Skype Empresarial Server.
  
Tenemos algunos diagramas de escenarios para ayudar a visualizar y decidir qué tipo Skype Empresarial Server topología de servidor perimetral que desea implementar. Una vez que hayas elegido un buen candidato, puedes leer los requisitos del entorno que tendrás que abordar. Lo siguiente es aplicable a cualquiera de los escenarios, por lo que lo mencionamos primero.
  
Estas cifras, que se muestran solo para fines de ejemplo (y como tales contienen datos de ejemplo IPv4 e IPv6), no representan el flujo de comunicación real, sino una vista de alto nivel del tráfico posible. Los detalles del puerto también se pueden ver en los diagramas de puerto para cada escenario siguiente.
  
Los diagramas muestran .com para la interfaz externa y .net para el interno, que también es material de muestra; por supuesto, sus propias entradas pueden ser muy diferentes cuando está armando su propio plan perimetral final.
  
No se incluye el director (que es un componente opcional) en ninguno de los diagramas, pero puede leerlo por separado (se menciona en otros temas de planeación).
  
Como se mencionó anteriormente, hay datos IPv6 de ejemplo en los diagramas. La mayoría de la documentación de [Plan for Edge Server deployments in Skype Empresarial Server](edge-server-deployments.md) hará referencia a IPv4, pero ciertamente se le admite si desea usar IPv6. Ten en cuenta que necesitarás direcciones IPv6 en el espacio de direcciones asignado y que necesitarán trabajar con direcciones internas y externas, como con IPv4 IPs. Puedes, gracias a Windows, usar la característica de pila dual, que es una pila de red independiente y distinta para IPv4 e IPv6. Esto le permitirá asignar direcciones IPv4 e IPv6 simultáneamente.
  
Hay dispositivos NAT que permiten NAT64 (IPv6 a IPv4) y NAT66 (IPv6 a IPv6)) y esto es válido para su uso con Skype Empresarial Server.
  
> [!IMPORTANT]
> Si usa el Control de admisión de llamadas (CAC), debe usar IPv4 en la interfaz interna para que funcione. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Servidor perimetral Skype Empresarial Server consolidado único con direcciones IP privadas y NAT

Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significará que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es imprescindible, consulte los siguientes escenarios consolidados escalados.
  
![Escenario perimetral para un único servidor perimetral consolidado con IP privada mediante NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama de puertos para servidores perimetrales consolidados únicos.
  
![Perímetro de red para escenario perimetral Único perimetral consolidado](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Servidor perimetral consolidado Skype Empresarial Server único con direcciones IP públicas

Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significará que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es imprescindible, consulte los siguientes escenarios consolidados escalados.
  
![Escenario perimetral para un único servidor perimetral consolidado con IP pública](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama de puertos para servidores perimetrales consolidados únicos.
  
![Perímetro de red para escenario perimetral Único perimetral consolidado](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Grupo perimetral consolidado Skype Empresarial Server escalado, con equilibrio de carga DNS y direcciones IP privadas y NAT

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con conmutación por error.
  
![Escenario perimetral para edge consolidado escalado, DNS LB con IP privada con NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama para grupos perimetrales consolidados escalados con equilibrio de carga DNS.
  
![Perímetro de red para escenario perimetral perimetral consolidado escalado con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Grupo perimetral consolidado Skype Empresarial Server escalado, con equilibrio de carga DNS y direcciones IP públicas

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con conmutación por error.
  
![Escenario perimetral para edge consolidado escalado, DNS LB con IP pública](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama para grupos perimetrales consolidados escalados con equilibrio de carga DNS.
  
![Perímetro de red para escenario perimetral perimetral consolidado escalado con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Grupo perimetral consolidado Skype Empresarial Server escalado, con equilibrio de carga de hardware

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con conmutación por error.
  
![Escenario perimetral para perímetro consolidado escalado con HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
