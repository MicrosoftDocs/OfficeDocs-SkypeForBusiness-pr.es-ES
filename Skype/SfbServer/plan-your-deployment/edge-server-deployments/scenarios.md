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
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813800"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Escenarios de servidor perimetral en Skype Empresarial Server
 
**Resumen:** Revise estos escenarios para ayudarle a planear la topología del servidor perimetral en Skype Empresarial Server.
  
Tenemos algunos diagramas de escenarios para ayudar a visualizar y decidir qué topología de servidor perimetral de Skype Empresarial Server desea implementar. Una vez que haya elegido un buen candidato, puede leer los requisitos del entorno que deberá cumplir. Lo siguiente es aplicable a cualquiera de los escenarios, por lo que lo mencionamos primero.
  
Estas cifras, que se muestran solo con fines de ejemplo (y como tal contienen datos de ejemplo IPv4 e IPv6), no representan el flujo de comunicación real, sino una vista de alto nivel del tráfico posible. Los detalles del puerto también se pueden ver en los diagramas de puerto para cada escenario siguiente.
  
Los diagramas muestran .com para la interfaz externa y .net para el interno, que también es material de ejemplo; Por supuesto, sus propias entradas pueden ser bastante diferentes cuando está reúnendo su propio plan perimetral final.
  
No se incluye el director (que es un componente opcional) en ninguno de los diagramas, pero puede leerlo por separado (se menciona en otros temas de planeación).
  
Como se indicó anteriormente, hay datos IPv6 de ejemplo en los diagramas. La mayor parte de la documentación de [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) hará referencia a IPv4, pero ciertamente es compatible si desea usar IPv6. Ten en cuenta que necesitarás direcciones IPv6 en el espacio de direcciones asignado y direccionamientos internos y externos, como con las DIRECCIONES IP IPv4. Puedes, gracias a Windows, usar la característica de pila dual, que es una pila de red independiente y distinta para IPv4 e IPv6. Esto le permitirá, si lo necesita, asignar direcciones IPv4 e IPv6 simultáneamente.
  
Hay dispositivos NAT que permiten NAT64 (IPv6 a IPv4) y NAT66 (IPv6 a IPv6)) y esto es válido para su uso con Skype Empresarial Server.
  
> [!IMPORTANT]
> Si usa el servicio de control de admisión de llamadas (CAC), debe usar IPv4 en la interfaz interna para que funcione. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Servidor perimetral de Skype Empresarial Server consolidado único con direcciones IP privadas y NAT

Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significa que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es imprescindible, consulte los siguientes escenarios consolidados escalados.
  
![Escenario perimetral para servidor perimetral consolidado único con IP privada mediante NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama de puertos para servidores perimetrales consolidados únicos.
  
![Perímetro de red para perímetro consolidado único de escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Servidor perimetral de Skype Empresarial Server consolidado único con direcciones IP públicas

Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significa que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es imprescindible, consulte los siguientes escenarios consolidados escalados.
  
![Escenario perimetral para servidor perimetral consolidado único con IP pública](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama de puertos para servidores perimetrales consolidados únicos.
  
![Perímetro de red para perímetro consolidado único de escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Grupo perimetral consolidado de Skype Empresarial Server escalado, con equilibrio de carga DNS, direcciones IP privadas y NAT

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.
  
![Escenario perimetral para servidor perimetral consolidado escalado, LB de DNS con IP privada mediante NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama para grupos de servidores perimetrales consolidados escalados con equilibrio de carga de DNS.
  
![Perímetro de red para perímetro consolidado escalado de escenario perimetral mediante DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Grupo perimetral consolidado de Skype Empresarial Server escalado, con equilibrio de carga DNS y direcciones IP públicas

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.
  
![Escenario perimetral para servidor perimetral consolidado escalado, LB de DNS con IP pública](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de puertos

También tenemos un diagrama para grupos de servidores perimetrales consolidados escalados con equilibrio de carga de DNS.
  
![Perímetro de red para perímetro consolidado escalado de escenario perimetral mediante DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Grupo perimetral consolidado escalado de Skype Empresarial Server, con equilibrio de carga de hardware

Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.
  
![Escenario perimetral para servidor perimetral consolidado escalado con HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
