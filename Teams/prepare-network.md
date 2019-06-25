---
title: Preparar la red de la organización para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
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
ms.openlocfilehash: d203aefa4ba6991fbe6cf6a2ac463f4649f2aaa9
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198424"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="d8e7e-104">Preparar la red de la organización para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8e7e-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="d8e7e-105">Teams combina tres formas de tráfico:</span><span class="sxs-lookup"><span data-stu-id="d8e7e-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="d8e7e-106">Tráfico de datos entre el entorno en línea de Office 365 y el cliente de Teams (señalización, presencia, chat, carga y descarga de archivos, sincronización de OneNote).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="d8e7e-107">Tráfico de comunicaciones punto a punto en tiempo real (audio, vídeo y escritorio compartido).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="d8e7e-108">Tráfico de comunicaciones de conferencias en tiempo real (audio, vídeo y escritorio compartido).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="d8e7e-p102">Esto afecta la red de dos maneras: el tráfico fluirá entre los clientes de Microsoft Teams directamente para las comunicaciones de par a par, y entre el entorno de Office 365 y los clientes de Microsoft Teams en los escenarios de reuniones. Para asegurar un flujo de tráfico óptimo, se debe permitir que el tráfico fluya entre los segmentos de red internos (por ejemplo, entre sitios a través de WAN), así como entre los sitios de red y Office 365. Si no se abren los puertos correctos o se bloquean activamente determinados puertos, se obtendrá una experiencia deficiente.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="d8e7e-112">Las reuniones son compatibles con dispositivos móviles iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="d8e7e-113">Para obtener una experiencia óptima con medios en tiempo real en Microsoft Teams, su red debe cumplir con los requisitos de red de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="d8e7e-114">Para obtener más información, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="d8e7e-115">Para los dos segmentos de red definitivos (cliente a Microsoft Edge y perímetro de cliente a Microsoft Edge), tenga en cuenta las siguientes recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="d8e7e-116">Valor</span><span class="sxs-lookup"><span data-stu-id="d8e7e-116">Value</span></span>  |<span data-ttu-id="d8e7e-117">Cliente a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d8e7e-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="d8e7e-118">Perímetro de cliente a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d8e7e-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="d8e7e-119">**Latencia (unidireccional)**\*</span><span class="sxs-lookup"><span data-stu-id="d8e7e-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="d8e7e-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="d8e7e-120">< 50ms</span></span>          |<span data-ttu-id="d8e7e-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="d8e7e-121">< 30ms</span></span>         |
|<span data-ttu-id="d8e7e-122">**Latencia (RTT o tiempo de ida y vuelta)**\*</span><span class="sxs-lookup"><span data-stu-id="d8e7e-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="d8e7e-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="d8e7e-123">< 100ms</span></span>   |<span data-ttu-id="d8e7e-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="d8e7e-124">< 60ms</span></span> |
|<span data-ttu-id="d8e7e-125">**Pérdida de paquetes de ráfaga**</span><span class="sxs-lookup"><span data-stu-id="d8e7e-125">**Burst packet loss**</span></span>    |<span data-ttu-id="d8e7e-126">< 10% durante un intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="d8e7e-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="d8e7e-127">< 1% durante un intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="d8e7e-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="d8e7e-128">**Pérdida de paquetes**</span><span class="sxs-lookup"><span data-stu-id="d8e7e-128">**Packet loss**</span></span>     |<span data-ttu-id="d8e7e-129">< 1% durante un intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="d8e7e-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="d8e7e-130">< 0,1% durante un intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="d8e7e-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="d8e7e-131">**Vibración entre llegadas de paquetes**</span><span class="sxs-lookup"><span data-stu-id="d8e7e-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="d8e7e-132">< 30 ms durante un intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="d8e7e-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="d8e7e-133">< 15 ms durante un intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="d8e7e-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="d8e7e-134">**Reordenamiento de paquetes**</span><span class="sxs-lookup"><span data-stu-id="d8e7e-134">**Packet reorder**</span></span>    |<span data-ttu-id="d8e7e-135">< 0,05% paquetes sin ordenar</span><span class="sxs-lookup"><span data-stu-id="d8e7e-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="d8e7e-136">< 0,01% paquetes sin ordenar</span><span class="sxs-lookup"><span data-stu-id="d8e7e-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="d8e7e-137">\*El objetivo de la métrica de latencia supone que el sitio o los sitios de la empresa y los bordes de Microsoft están en el mismo continente.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="d8e7e-138">La conexión del sitio de su empresa con el perímetro de la red de Microsoft incluye acceso de red de primer salto, que puede ser WiFi u otra tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="d8e7e-139">Los objetivos de rendimiento de red suponen un ancho de banda adecuado o un [plan QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="d8e7e-140">En otras palabras, los requisitos se aplican directamente al tráfico de medios en tiempo real de Teams cuando la conexión de red está por debajo de una carga máxima.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="d8e7e-141">Para probar los dos segmentos de red, puede usar la [herramienta de evaluación de red](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="d8e7e-142">Esta herramienta se puede implementar tanto en el PC cliente directamente como en un equipo PC conectado al perímetro de la red del cliente.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="d8e7e-143">La herramienta incluye documentación limitada, pero una documentación más profunda sobre el uso de la herramienta puede encontrarse aquí: evaluación de la preparación para la [red](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="d8e7e-144">Al ejecutar esta evaluación de la disponibilidad de la red, puede validar la preparación de su red para ejecutar aplicaciones de medios en tiempo real, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="d8e7e-145">Esta es la misma evaluación de disponibilidad de red que se recomienda ejecutar para los clientes que desean implementar Skype empresarial correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="d8e7e-146">Requisitos de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="d8e7e-146">Bandwidth requirements</span></span>
<span data-ttu-id="d8e7e-147">Microsoft Teams te ofrece la mejor experiencia de audio, vídeo y uso compartido de contenido, independientemente de las condiciones de tu red.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="d8e7e-148">Con los códecs variables, los medios se pueden negociar en entornos de ancho de banda limitados con un impacto mínimo.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="d8e7e-149">Pero donde el ancho de banda no es un problema, las experiencias se pueden optimizar para la calidad, incluida la resolución de video de 1080p, hasta 30 fps para video y 15fps para el contenido y el audio de alta fidelidad.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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

<a name="additional-network-considerations"></a><span data-ttu-id="d8e7e-150">Consideraciones de red adicionales</span><span class="sxs-lookup"><span data-stu-id="d8e7e-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="d8e7e-151">Resolución de nombres externos</span><span class="sxs-lookup"><span data-stu-id="d8e7e-151">External Name Resolution</span></span>

<span data-ttu-id="d8e7e-152">Asegúrese de que todos los equipos cliente que ejecutan el cliente de Teams puedan resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365 y que los firewalls no impiden el acceso.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="d8e7e-153">Para obtener información sobre cómo configurar puertos de firewall, vaya a [Office 365 URL e intervalos IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="d8e7e-154">Tamaño del grupo NAT</span><span class="sxs-lookup"><span data-stu-id="d8e7e-154">NAT Pool Size</span></span>

<span data-ttu-id="d8e7e-155">Cuando varios usuarios o dispositivos obtienen acceso a Office 365 mediante la traducción de direcciones de red (NAT) o la traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos que se encuentran detrás de cada dirección IP enrutable pública no superen el número admitido.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="d8e7e-156">Para mitigar este riesgo, asegúrese de que se asignan direcciones IP públicas adecuadas a los grupos NAT para evitar el agotamiento del puerto.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="d8e7e-157">El agotamiento del puerto provocará problemas a los usuarios finales internos y los dispositivos al conectarse a los servicios 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="d8e7e-158">Para obtener más información, consulte [compatibilidad de NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="d8e7e-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="d8e7e-159">**Guía de detección y prevención de intrusiones**</span><span class="sxs-lookup"><span data-stu-id="d8e7e-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="d8e7e-160">Si su entorno tiene un sistema de detección o prevención de intrusiones (IDS/IPS) implementado para una capa adicional de seguridad para conexiones salientes, asegúrese de que todo el tráfico con destino a las direcciones URL de Office 365 se encuentra en la lista blanca.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="d8e7e-161">Determinación del estado de la red</span><span class="sxs-lookup"><span data-stu-id="d8e7e-161">Network health determination</span></span>
-----------------

<span data-ttu-id="d8e7e-162">Al planear la implementación de Microsoft Teams en su red, debe asegurarse de que tiene el ancho de banda necesario, que tiene acceso a todas las direcciones IP requeridas, que se han abierto los puertos correctos y que está cumpliendo los requisitos de rendimiento para los medios en tiempo real .</span><span class="sxs-lookup"><span data-stu-id="d8e7e-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="d8e7e-163">Si sabe que no cumplirá estos criterios, los usuarios finales no obtendrán una experiencia óptima de Teams debido a la mala calidad de las llamadas y las reuniones.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="d8e7e-164">Si no cumple estos criterios, es el momento de considerar pausar el proyecto para asegurarse de que cumple los criterios antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="d8e7e-166">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="d8e7e-166">Decision Point</span></span>         |<span data-ttu-id="d8e7e-167">¿Ha evaluado sus capacidades de red para admitir medios en tiempo real?</span><span class="sxs-lookup"><span data-stu-id="d8e7e-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="d8e7e-168">Si su red no se ha evaluado correctamente o sabe que no es compatible con los medios en tiempo real, deshabilitará las funciones de vídeo y pantalla compartida para reducir el impacto de la red y las experiencias de equipos deficientes.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Un icono que representa los pasos siguientes](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="d8e7e-170">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="d8e7e-170">Next Steps</span></span>         |<span data-ttu-id="d8e7e-171">Calidad de red desconocida: realice una evaluación de la disponibilidad de red para determinar si su red está lista para los medios en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-171">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="d8e7e-172">Calidad de red deficiente: realice los pasos de corrección de red para proporcionar un entorno adecuado para los medios en tiempo real de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="d8e7e-173">Red satisfactoria: Asegúrese de que todas las direcciones IP y los puertos son accesibles correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8e7e-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="d8e7e-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d8e7e-174">Related Topics</span></span>

[<span data-ttu-id="d8e7e-175">Vídeo: planificación de red</span><span class="sxs-lookup"><span data-stu-id="d8e7e-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
