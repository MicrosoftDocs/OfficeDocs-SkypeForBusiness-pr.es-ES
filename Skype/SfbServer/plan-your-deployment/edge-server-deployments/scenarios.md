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
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="bb12d-103">Escenarios de servidor perimetral en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bb12d-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="bb12d-104">**Resumen:** Revise estos escenarios para ayudarle a planear la topología del servidor perimetral en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bb12d-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="bb12d-105">Tenemos algunos diagramas de escenarios para ayudar a visualizar y decidir qué topología de servidor perimetral de Skype Empresarial Server desea implementar.</span><span class="sxs-lookup"><span data-stu-id="bb12d-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="bb12d-106">Una vez que haya elegido un buen candidato, puede leer los requisitos del entorno que deberá cumplir.</span><span class="sxs-lookup"><span data-stu-id="bb12d-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="bb12d-107">Lo siguiente es aplicable a cualquiera de los escenarios, por lo que lo mencionamos primero.</span><span class="sxs-lookup"><span data-stu-id="bb12d-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="bb12d-108">Estas cifras, que se muestran solo con fines de ejemplo (y como tal contienen datos de ejemplo IPv4 e IPv6), no representan el flujo de comunicación real, sino una vista de alto nivel del tráfico posible.</span><span class="sxs-lookup"><span data-stu-id="bb12d-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="bb12d-109">Los detalles del puerto también se pueden ver en los diagramas de puerto para cada escenario siguiente.</span><span class="sxs-lookup"><span data-stu-id="bb12d-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="bb12d-110">Los diagramas muestran .com para la interfaz externa y .net para el interno, que también es material de ejemplo; Por supuesto, sus propias entradas pueden ser bastante diferentes cuando está reúnendo su propio plan perimetral final.</span><span class="sxs-lookup"><span data-stu-id="bb12d-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="bb12d-111">No se incluye el director (que es un componente opcional) en ninguno de los diagramas, pero puede leerlo por separado (se menciona en otros temas de planeación).</span><span class="sxs-lookup"><span data-stu-id="bb12d-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="bb12d-112">Como se indicó anteriormente, hay datos IPv6 de ejemplo en los diagramas.</span><span class="sxs-lookup"><span data-stu-id="bb12d-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="bb12d-113">La mayor parte de la documentación de [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) hará referencia a IPv4, pero ciertamente es compatible si desea usar IPv6.</span><span class="sxs-lookup"><span data-stu-id="bb12d-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="bb12d-114">Ten en cuenta que necesitarás direcciones IPv6 en el espacio de direcciones asignado y direccionamientos internos y externos, como con las DIRECCIONES IP IPv4.</span><span class="sxs-lookup"><span data-stu-id="bb12d-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="bb12d-115">Puedes, gracias a Windows, usar la característica de pila dual, que es una pila de red independiente y distinta para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="bb12d-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="bb12d-116">Esto le permitirá, si lo necesita, asignar direcciones IPv4 e IPv6 simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="bb12d-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="bb12d-117">Hay dispositivos NAT que permiten NAT64 (IPv6 a IPv4) y NAT66 (IPv6 a IPv6)) y esto es válido para su uso con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bb12d-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb12d-118">Si usa el servicio de control de admisión de llamadas (CAC), debe usar IPv4 en la interfaz interna para que funcione.</span><span class="sxs-lookup"><span data-stu-id="bb12d-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="bb12d-119">Servidor perimetral de Skype Empresarial Server consolidado único con direcciones IP privadas y NAT</span><span class="sxs-lookup"><span data-stu-id="bb12d-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="bb12d-120">Con este escenario, no hay ninguna opción para la alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="bb12d-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="bb12d-121">Esto significa que gastará menos en hardware y tendrá una implementación más sencilla.</span><span class="sxs-lookup"><span data-stu-id="bb12d-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="bb12d-122">Si la alta disponibilidad es imprescindible, consulte los siguientes escenarios consolidados escalados.</span><span class="sxs-lookup"><span data-stu-id="bb12d-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Escenario perimetral para servidor perimetral consolidado único con IP privada mediante NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="bb12d-124">Diagrama de puertos</span><span class="sxs-lookup"><span data-stu-id="bb12d-124">Port diagram</span></span>

<span data-ttu-id="bb12d-125">También tenemos un diagrama de puertos para servidores perimetrales consolidados únicos.</span><span class="sxs-lookup"><span data-stu-id="bb12d-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de red para perímetro consolidado único de escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="bb12d-127">Servidor perimetral de Skype Empresarial Server consolidado único con direcciones IP públicas</span><span class="sxs-lookup"><span data-stu-id="bb12d-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="bb12d-128">Con este escenario, no hay ninguna opción para la alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="bb12d-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="bb12d-129">Esto significa que gastará menos en hardware y tendrá una implementación más sencilla.</span><span class="sxs-lookup"><span data-stu-id="bb12d-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="bb12d-130">Si la alta disponibilidad es imprescindible, consulte los siguientes escenarios consolidados escalados.</span><span class="sxs-lookup"><span data-stu-id="bb12d-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Escenario perimetral para servidor perimetral consolidado único con IP pública](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="bb12d-132">Diagrama de puertos</span><span class="sxs-lookup"><span data-stu-id="bb12d-132">Port diagram</span></span>

<span data-ttu-id="bb12d-133">También tenemos un diagrama de puertos para servidores perimetrales consolidados únicos.</span><span class="sxs-lookup"><span data-stu-id="bb12d-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perímetro de red para perímetro consolidado único de escenario perimetral](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="bb12d-135">Grupo perimetral consolidado de Skype Empresarial Server escalado, con equilibrio de carga DNS, direcciones IP privadas y NAT</span><span class="sxs-lookup"><span data-stu-id="bb12d-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="bb12d-136">Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="bb12d-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Escenario perimetral para servidor perimetral consolidado escalado, LB de DNS con IP privada mediante NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="bb12d-138">Diagrama de puertos</span><span class="sxs-lookup"><span data-stu-id="bb12d-138">Port diagram</span></span>

<span data-ttu-id="bb12d-139">También tenemos un diagrama para grupos de servidores perimetrales consolidados escalados con equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="bb12d-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de red para perímetro consolidado escalado de escenario perimetral mediante DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="bb12d-141">Grupo perimetral consolidado de Skype Empresarial Server escalado, con equilibrio de carga DNS y direcciones IP públicas</span><span class="sxs-lookup"><span data-stu-id="bb12d-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="bb12d-142">Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="bb12d-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Escenario perimetral para servidor perimetral consolidado escalado, LB de DNS con IP pública](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="bb12d-144">Diagrama de puertos</span><span class="sxs-lookup"><span data-stu-id="bb12d-144">Port diagram</span></span>

<span data-ttu-id="bb12d-145">También tenemos un diagrama para grupos de servidores perimetrales consolidados escalados con equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="bb12d-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perímetro de red para perímetro consolidado escalado de escenario perimetral mediante DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="bb12d-147">Grupo perimetral consolidado escalado de Skype Empresarial Server, con equilibrio de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="bb12d-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="bb12d-148">Con este escenario, puede tener alta disponibilidad en la implementación perimetral, lo que le ofrece las ventajas de la escalabilidad y la compatibilidad con la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="bb12d-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Escenario perimetral para servidor perimetral consolidado escalado con HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
