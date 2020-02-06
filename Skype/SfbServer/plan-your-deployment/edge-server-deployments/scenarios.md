---
title: Escenarios de servidores perimetrales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Revise estos escenarios para ayudarle a planear la topología de servidores perimetrales en Skype empresarial Server.'
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803360"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="b994a-103">Escenarios de servidores perimetrales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b994a-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="b994a-104">**Resumen:** Revise estos escenarios para ayudarle a planear la topología del servidor perimetral en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b994a-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="b994a-105">Tenemos algunos diagramas de escenarios que le ayudarán a visualizar y a decidir qué topología de servidor perimetral de Skype empresarial Server desea implementar.</span><span class="sxs-lookup"><span data-stu-id="b994a-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="b994a-106">Una vez que haya seleccionado un buen candidato, puede leer los requisitos del entorno que tendrá que abordar.</span><span class="sxs-lookup"><span data-stu-id="b994a-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="b994a-107">Lo siguiente se aplica a cualquiera de los escenarios, por lo que lo mencionamos primero.</span><span class="sxs-lookup"><span data-stu-id="b994a-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="b994a-p102">Estas ilustraciones, que se muestran solo con fines de ejemplo (y como tal contienen ejemplos de datos de IPv4 e IPv6), no representan el flujo de comunicación real, sino una vista de alto nivel de su posible tráfico. También se puede ver información de los puertos en los Diagramas de puertos para cada escenario que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="b994a-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="b994a-110">Los diagramas muestran .com para la interfaz externa y .net para la interna, que también es material de muestra. Por supuesto, sus propias entradas pueden ser muy diferentes cuando esté elaborando su propio plan perimetral final.</span><span class="sxs-lookup"><span data-stu-id="b994a-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="b994a-111">No incluimos el director (que es un componente opcional) en ninguno de los diagramas, pero puede leer sobre esto por separado (se menciona en otros temas de planificación).</span><span class="sxs-lookup"><span data-stu-id="b994a-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="b994a-112">Como se indica anteriormente, hay datos de ejemplo de IPv6 en los diagramas.</span><span class="sxs-lookup"><span data-stu-id="b994a-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="b994a-113">La mayor parte de la documentación del [plan de implementaciones de servidores perimetrales en Skype empresarial Server](edge-server-deployments.md) hará referencia a IPv4, pero ciertamente es compatible Si desea usar IPv6.</span><span class="sxs-lookup"><span data-stu-id="b994a-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="b994a-114">Tenga en cuenta que necesitará direcciones IPv6 en el espacio de direcciones asignadas y que tendrán que funcionar con el direccionamiento interno y el externo, al igual que con IP de IPv4.</span><span class="sxs-lookup"><span data-stu-id="b994a-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="b994a-115">Puede, con Windows, recurrir a la característica de pila doble, que es una pila de red diferente y separada para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="b994a-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="b994a-116">Esto permitirá, si lo necesita, asignar las direcciones IPv4 e IPv6 simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="b994a-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="b994a-117">Existen dispositivos NAT que permiten para NAT64 (IPv6 a IPv4) y NAT66 (IPv6 a IPv6)), y esto es válido para usar con Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b994a-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b994a-118">Si está usando el servicio de control de admisión de llamadas (CAC), tiene que usar IPv4 en la interfaz interna para que funcione.</span><span class="sxs-lookup"><span data-stu-id="b994a-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="b994a-119">Un único servidor perimetral de Skype empresarial Server con direcciones IP privadas y NAT</span><span class="sxs-lookup"><span data-stu-id="b994a-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="b994a-p104">Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significa que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es una necesidad, compruebe los escenarios consolidados ampliados a continuación.</span><span class="sxs-lookup"><span data-stu-id="b994a-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Escenario perimetral para el perímetro consolidado único con IP privada por medio de NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b994a-124">Diagrama de puerto</span><span class="sxs-lookup"><span data-stu-id="b994a-124">Port diagram</span></span>

<span data-ttu-id="b994a-125">También tenemos un diagrama de puertos para servidores únicos consolidados.</span><span class="sxs-lookup"><span data-stu-id="b994a-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="b994a-127">Un único servidor perimetral de Skype empresarial Server con direcciones IP públicas</span><span class="sxs-lookup"><span data-stu-id="b994a-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="b994a-p105">Con este escenario, no hay ninguna opción para la alta disponibilidad. Esto significa que gastará menos en hardware y tendrá una implementación más sencilla. Si la alta disponibilidad es una necesidad, compruebe los escenarios consolidados ampliados a continuación.</span><span class="sxs-lookup"><span data-stu-id="b994a-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Escenario perimetral para el perímetro consolidado único con IP pública](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b994a-132">Diagrama de puerto</span><span class="sxs-lookup"><span data-stu-id="b994a-132">Port diagram</span></span>

<span data-ttu-id="b994a-133">También tenemos un diagrama de puertos para servidores únicos consolidados.</span><span class="sxs-lookup"><span data-stu-id="b994a-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="b994a-135">Grupo concentrado de Skype empresarial consolidado escalado, con equilibrio de carga de DNS, y direcciones IP privadas y NAT</span><span class="sxs-lookup"><span data-stu-id="b994a-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="b994a-136">Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le proporciona las ventajas de escalabilidad y compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b994a-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Escenario perimetral para el perímetro consolidado escalado, equilibrador de carga de DNS con IP privada por medio de NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b994a-138">Diagrama de puerto</span><span class="sxs-lookup"><span data-stu-id="b994a-138">Port diagram</span></span>

<span data-ttu-id="b994a-139">También tenemos un diagrama de grupos de límites consolidados con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="b994a-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral con equilibrador de carga de DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="b994a-141">Grupo de servidores perimetrales de Skype empresarial consolidado escalado con equilibrio de carga DNS y direcciones IP públicas</span><span class="sxs-lookup"><span data-stu-id="b994a-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="b994a-142">Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le proporciona las ventajas de escalabilidad y compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b994a-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Escenario perimetral para el perímetro consolidado escalado, equilibrador de carga de DNS con IP pública](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b994a-144">Diagrama de puerto</span><span class="sxs-lookup"><span data-stu-id="b994a-144">Port diagram</span></span>

<span data-ttu-id="b994a-145">También tenemos un diagrama de grupos de límites consolidados con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="b994a-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de la red para el perímetro consolidado escalado del escenario perimetral con equilibrador de carga de DNS](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="b994a-147">Grupo de servidores perimetrales de Skype empresarial consolidado escalado con equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="b994a-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="b994a-148">Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le proporciona las ventajas de escalabilidad y compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b994a-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Escenario perimetral para el perímetro consolidado escalado con equilibrador de carga de hardware](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
