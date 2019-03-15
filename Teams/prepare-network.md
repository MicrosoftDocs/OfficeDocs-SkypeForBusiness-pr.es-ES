---
title: Preparar la red de la organización para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Sepa cómo preparar y administrar la red de Microsoft Teams. La información incluye los requisitos de red, los requisitos de ancho de banda y otras consideraciones.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640733"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="48bf9-104">Preparar la red de la organización para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48bf9-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="48bf9-105">Vea la sesión siguiente para obtener más información cómo los equipos aprovecha la red y cómo planear mejor para la conectividad de red óptima: [Planeación de los equipos de red](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="48bf9-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="48bf9-106">Los equipos combina tres formas de tráfico:</span><span class="sxs-lookup"><span data-stu-id="48bf9-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="48bf9-107">Tráfico de datos entre el entorno de Office 365 en línea y el cliente de los equipos (señalización, presencia, chat, carga de archivos y descarga, sincronización de OneNote).</span><span class="sxs-lookup"><span data-stu-id="48bf9-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="48bf9-108">Tráfico de comunicaciones en tiempo real de punto a punto (audio, vídeo, escritorio uso compartido).</span><span class="sxs-lookup"><span data-stu-id="48bf9-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="48bf9-109">Tráfico de comunicaciones en tiempo real de conferencia (audio, vídeo, escritorio uso compartido).</span><span class="sxs-lookup"><span data-stu-id="48bf9-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="48bf9-110">Esto afecta a la red en dos niveles: fluirá el tráfico entre los clientes de Microsoft Teams directamente para escenarios de punto a punto y fluirá el tráfico entre el entorno de Office 365 y los clientes de Microsoft Teams para escenarios de la reunión.</span><span class="sxs-lookup"><span data-stu-id="48bf9-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="48bf9-111">Para garantizar un flujo de tráfico sea óptima, se debe permitir el tráfico de flujo de ambos entre los segmentos de red interna (por ejemplo, entre los sitios a través de la WAN), así como entre los sitios de red y Office 365.</span><span class="sxs-lookup"><span data-stu-id="48bf9-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="48bf9-112">No abrir los puertos adecuados o activamente el bloqueo de puertos específicos conducirá a una experiencia de degradado.</span><span class="sxs-lookup"><span data-stu-id="48bf9-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="48bf9-113">Las reuniones son compatibles con iOS y Android dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="48bf9-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="48bf9-114">Para obtener una experiencia óptima con multimedia en tiempo real dentro de Microsoft Teams, la red debe cumplir los requisitos de red para Office 365.</span><span class="sxs-lookup"><span data-stu-id="48bf9-114">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="48bf9-115">Para obtener más información, vea [calidad de los medios y el rendimiento de la conectividad de red para Skype para profesionales en línea](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="48bf9-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="48bf9-116">Para los dos definen segmentos de red (cliente a Microsoft Edge) y borde de cliente a Microsoft Edge, tenga en cuenta las siguientes recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="48bf9-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="48bf9-117">Valor</span><span class="sxs-lookup"><span data-stu-id="48bf9-117">Value</span></span>  |<span data-ttu-id="48bf9-118">Cliente hasta el borde de Microsoft</span><span class="sxs-lookup"><span data-stu-id="48bf9-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="48bf9-119">Borde de cliente hasta el borde de Microsoft</span><span class="sxs-lookup"><span data-stu-id="48bf9-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="48bf9-120">**Latencia (unidireccional)**\*</span><span class="sxs-lookup"><span data-stu-id="48bf9-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="48bf9-121">< 50 ms.</span><span class="sxs-lookup"><span data-stu-id="48bf9-121">< 50ms</span></span>          |<span data-ttu-id="48bf9-122">< 30ms</span><span class="sxs-lookup"><span data-stu-id="48bf9-122">< 30ms</span></span>         |
|<span data-ttu-id="48bf9-123">**Latencia (RTT o tiempo de ida y vuelta)**\*</span><span class="sxs-lookup"><span data-stu-id="48bf9-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="48bf9-124">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="48bf9-124">< 100ms</span></span>   |<span data-ttu-id="48bf9-125">< 60ms</span><span class="sxs-lookup"><span data-stu-id="48bf9-125">< 60ms</span></span> |
|<span data-ttu-id="48bf9-126">**Ráfagas de pérdida de paquetes**</span><span class="sxs-lookup"><span data-stu-id="48bf9-126">**Burst packet loss**</span></span>    |<span data-ttu-id="48bf9-127"><10% durante cualquier intervalo 200ms</span><span class="sxs-lookup"><span data-stu-id="48bf9-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="48bf9-128"><1% durante cualquier intervalo 200ms</span><span class="sxs-lookup"><span data-stu-id="48bf9-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="48bf9-129">**Pérdida de paquetes**</span><span class="sxs-lookup"><span data-stu-id="48bf9-129">**Packet loss**</span></span>     |<span data-ttu-id="48bf9-130"><1% durante cualquier 15s intervalo</span><span class="sxs-lookup"><span data-stu-id="48bf9-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="48bf9-131"><0.1% durante cualquier 15s intervalo</span><span class="sxs-lookup"><span data-stu-id="48bf9-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="48bf9-132">**Vibración de llegada entre granjas de paquetes**</span><span class="sxs-lookup"><span data-stu-id="48bf9-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="48bf9-133"><30ms durante cualquier 15s intervalo</span><span class="sxs-lookup"><span data-stu-id="48bf9-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="48bf9-134"><15ms durante cualquier 15s intervalo</span><span class="sxs-lookup"><span data-stu-id="48bf9-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="48bf9-135">**Reaprovisionamiento de paquetes**</span><span class="sxs-lookup"><span data-stu-id="48bf9-135">**Packet reorder**</span></span>    |<span data-ttu-id="48bf9-136">paquetes de salida de orden <0.05%</span><span class="sxs-lookup"><span data-stu-id="48bf9-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="48bf9-137">paquetes de salida de orden <0.01%</span><span class="sxs-lookup"><span data-stu-id="48bf9-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="48bf9-138">\*Los destinos de métricas de latencia asumen su sitio de empresa o los sitios y los bordes de Microsoft se encuentran en el mismo continente.</span><span class="sxs-lookup"><span data-stu-id="48bf9-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="48bf9-139">La conexión del sitio de empresa para el perímetro de red de Microsoft incluye primer salto acceso a la red, que puede ser WiFi u otra tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="48bf9-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="48bf9-140">Los objetivos de rendimiento de red suponen ancho de banda adecuado o [QoS de planeación](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="48bf9-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="48bf9-141">En otras palabras, los requisitos se aplican directamente al tráfico de medios en tiempo real de los equipos cuando la conexión de red está bajo una carga máxima.</span><span class="sxs-lookup"><span data-stu-id="48bf9-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="48bf9-142">Para probar ambos segmentos de red, puede usar la [Herramienta de evaluación de la red](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="48bf9-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="48bf9-143">Esta herramienta se puede implementar en el cliente PC directamente y en un PC conectado hasta el borde de la red del cliente.</span><span class="sxs-lookup"><span data-stu-id="48bf9-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="48bf9-144">La herramienta incluye documentación limitada, pero una documentación más profunda alrededor el uso de la herramienta se puede encontrar aquí: [Evaluación de preparación de la red](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="48bf9-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="48bf9-145">Mediante la ejecución de esta evaluación de disponibilidad de red, puede validar preparación de su red para ejecutar aplicaciones de multimedia en tiempo real, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="48bf9-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="48bf9-146">Este es el mismo Readiness Assessment de red que se recomienda que se ejecute para los clientes que desean para implementar correctamente Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="48bf9-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="48bf9-147">Requisitos de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="48bf9-147">Bandwidth requirements</span></span>

<span data-ttu-id="48bf9-148">Los cálculos de ancho de banda para Microsoft Teams son complejos y para ayudar a con esto, se ha creado una calculadora.</span><span class="sxs-lookup"><span data-stu-id="48bf9-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="48bf9-149">Para obtener acceso a la Calculadora, vaya al [Organizador de la red](https://aka.ms/bwcalc/) en MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="48bf9-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="48bf9-150">Mejora el control de ancho de banda de los equipos en Skype para profesionales en línea: para una alta calidad de llamada o reunión experiencia (con audio, vídeo y uso compartido), los equipos requiere sólo 1,2 Mbps.</span><span class="sxs-lookup"><span data-stu-id="48bf9-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="48bf9-151">También puede escalar más allá de super alta calidad si no hay suficiente ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="48bf9-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="48bf9-152">Cuando una solicitud de los equipos encuentra una condición de ancho de banda bajo, los equipos pueden reajustar rápidamente el uso de ancho de banda para adaptarse al ancho de banda disponible.</span><span class="sxs-lookup"><span data-stu-id="48bf9-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="48bf9-153">Consideraciones de red adicionales</span><span class="sxs-lookup"><span data-stu-id="48bf9-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="48bf9-154">Resolución de nombres externos</span><span class="sxs-lookup"><span data-stu-id="48bf9-154">External Name Resolution</span></span>

<span data-ttu-id="48bf9-155">Asegúrese de que todos los equipos cliente que ejecutan los equipos cliente pueden resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365, y que los firewalls no impiden el acceso.</span><span class="sxs-lookup"><span data-stu-id="48bf9-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="48bf9-156">Para obtener información acerca de cómo configurar los puertos de firewall, vaya a [las direcciones URL de Office 365 e intervalos IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="48bf9-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="48bf9-157">Tamaño del grupo de servidores NAT</span><span class="sxs-lookup"><span data-stu-id="48bf9-157">NAT Pool Size</span></span>

<span data-ttu-id="48bf9-158">Cuando varios usuarios o dispositivos acceso a Office 365 con traducción de direcciones de red (NAT) o traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos ocultos detrás de cada dirección IP enrutable públicamente no supera el número compatible.</span><span class="sxs-lookup"><span data-stu-id="48bf9-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="48bf9-159">Para mitigar este riesgo, asegúrese de direcciones IP públicas adecuadas se asignan a los grupos de NAT para evitar el agotamiento de puerto.</span><span class="sxs-lookup"><span data-stu-id="48bf9-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="48bf9-160">Agotamiento del puerto hará que los usuarios finales internos y los dispositivos hacer frente a problemas al conectarse a los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="48bf9-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="48bf9-161">Para obtener más información, vea [admitir NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="48bf9-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="48bf9-162">**Guía de prevención de detección de intrusiones e**</span><span class="sxs-lookup"><span data-stu-id="48bf9-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="48bf9-163">Si su entorno tiene una detección de intrusiones o sistema de prevención (identificadores/IP) implementado para obtener un nivel adicional de seguridad para las conexiones salientes, asegúrese de que todo el tráfico con destino a las direcciones URL de Office 365 está en la lista blanca.</span><span class="sxs-lookup"><span data-stu-id="48bf9-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="48bf9-164">Determinación de mantenimiento de red</span><span class="sxs-lookup"><span data-stu-id="48bf9-164">Network health determination</span></span>
-----------------

<span data-ttu-id="48bf9-165">Cuando planee en la implementación de Microsoft Teams dentro de la red, debe asegurarse de tener el ancho de banda, tiene acceso a todas las direcciones IP necesarias, los puertos adecuados que se abre, y se cumplen los requisitos de rendimiento para los medios en tiempo real .</span><span class="sxs-lookup"><span data-stu-id="48bf9-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="48bf9-166">Si sabe que no se cumplan estos criterios, los usuarios finales no obtendrá una experiencia óptima de los equipos debido a la mala calidad durante las llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="48bf9-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="48bf9-167">Debe no cumplan estos criterios, esto es el tiempo que se deben considerar pausar el proyecto para asegurarse de que cumple los criterios antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="48bf9-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="48bf9-169">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="48bf9-169">Decision Point</span></span>         |<span data-ttu-id="48bf9-170">¿Se evalúan las funciones de red para la compatibilidad con multimedia en tiempo real?</span><span class="sxs-lookup"><span data-stu-id="48bf9-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="48bf9-171">¿Si la red no se ha evaluado correctamente o si se sabe que no será compatible con multimedia en tiempo real, se deshabilitará vídeo y uso compartido de capacidades para reducir el impacto en la red y una mala experiencia de los equipos de pantalla?</span><span class="sxs-lookup"><span data-stu-id="48bf9-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Icono de Siguientes pasos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="48bf9-173">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="48bf9-173">Next Steps</span></span>         |<span data-ttu-id="48bf9-174">Calidad de red desconocido: siga las instrucciones de [Evaluación de disponibilidad de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) para determinar si la red está preparada para multimedia en tiempo Real.</span><span class="sxs-lookup"><span data-stu-id="48bf9-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="48bf9-175">Mala calidad de red: Realizar los pasos de corrección de red para proporcionar un entorno adecuado para alta calidad multimedia en tiempo Real.</span><span class="sxs-lookup"><span data-stu-id="48bf9-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="48bf9-176">Red satisfactorio: Asegúrese de todas las direcciones IP y puertos son accesibles correctamente.</span><span class="sxs-lookup"><span data-stu-id="48bf9-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="48bf9-177">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="48bf9-177">Related Topics</span></span>

[<span data-ttu-id="48bf9-178">Vídeo: Planeación de red</span><span class="sxs-lookup"><span data-stu-id="48bf9-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)