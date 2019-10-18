---
title: Preparar la red de la organización para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Sepa cómo preparar y administrar la red de Microsoft Teams. La información incluye los requisitos de red, los requisitos de ancho de banda y otras consideraciones.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9013eb1048d022244166906edb1737b01757ed6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567690"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="5afaa-104">Preparar la red de la organización para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5afaa-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="5afaa-105">Teams combina tres formas de tráfico:</span><span class="sxs-lookup"><span data-stu-id="5afaa-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="5afaa-106">Tráfico de datos entre el entorno en línea de Office 365 y el cliente de Teams (señalización, presencia, chat, carga y descarga de archivos, sincronización de OneNote).</span><span class="sxs-lookup"><span data-stu-id="5afaa-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="5afaa-107">Tráfico de comunicaciones punto a punto en tiempo real (audio, vídeo y escritorio compartido).</span><span class="sxs-lookup"><span data-stu-id="5afaa-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="5afaa-108">Tráfico de comunicaciones de conferencias en tiempo real (audio, vídeo y escritorio compartido).</span><span class="sxs-lookup"><span data-stu-id="5afaa-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="5afaa-p102">Esto afecta la red de dos maneras: el tráfico fluirá entre los clientes de Microsoft Teams directamente para las comunicaciones de par a par, y entre el entorno de Office 365 y los clientes de Microsoft Teams en los escenarios de reuniones. Para asegurar un flujo de tráfico óptimo, se debe permitir que el tráfico fluya entre los segmentos de red internos (por ejemplo, entre sitios a través de WAN), así como entre los sitios de red y Office 365. Si no se abren los puertos correctos o se bloquean activamente determinados puertos, se obtendrá una experiencia deficiente.</span><span class="sxs-lookup"><span data-stu-id="5afaa-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>


<span data-ttu-id="5afaa-112">Para obtener una experiencia óptima con medios en tiempo real en Microsoft Teams, su red debe cumplir con los requisitos de red de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5afaa-112">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="5afaa-113">Para obtener más información, consulte calidad de los [medios y rendimiento de conectividad de red para Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="5afaa-113">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="5afaa-114">Para los dos segmentos de red que se definen (del cliente al Microsoft Edge y del extremo del cliente a Microsoft Edge), tenga en cuenta las siguientes recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="5afaa-114">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="5afaa-115">Valor</span><span class="sxs-lookup"><span data-stu-id="5afaa-115">Value</span></span>  |<span data-ttu-id="5afaa-116">Cliente a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5afaa-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="5afaa-117">Borde del cliente a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5afaa-117">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="5afaa-118">**Latencia (unidireccional)**\*</span><span class="sxs-lookup"><span data-stu-id="5afaa-118">**Latency (one way)** \*</span></span>  |<span data-ttu-id="5afaa-119">< 50ms</span><span class="sxs-lookup"><span data-stu-id="5afaa-119">< 50ms</span></span>          |<span data-ttu-id="5afaa-120">< 30ms</span><span class="sxs-lookup"><span data-stu-id="5afaa-120">< 30ms</span></span>         |
|<span data-ttu-id="5afaa-121">**Latencia (RTT o tiempo de ida y vuelta)**\*</span><span class="sxs-lookup"><span data-stu-id="5afaa-121">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="5afaa-122">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="5afaa-122">< 100ms</span></span>   |<span data-ttu-id="5afaa-123">< 60ms</span><span class="sxs-lookup"><span data-stu-id="5afaa-123">< 60ms</span></span> |
|<span data-ttu-id="5afaa-124">**Pérdida de paquetes en ráfagas**</span><span class="sxs-lookup"><span data-stu-id="5afaa-124">**Burst packet loss**</span></span>    |<span data-ttu-id="5afaa-125"><el 10% durante cualquier intervalo de 200ms</span><span class="sxs-lookup"><span data-stu-id="5afaa-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="5afaa-126"><1% durante cualquier intervalo de 200ms</span><span class="sxs-lookup"><span data-stu-id="5afaa-126"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="5afaa-127">**Pérdida de paquetes**</span><span class="sxs-lookup"><span data-stu-id="5afaa-127">**Packet loss**</span></span>     |<span data-ttu-id="5afaa-128"><1% durante cualquier intervalo de 15S</span><span class="sxs-lookup"><span data-stu-id="5afaa-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="5afaa-129"><0,1% durante cualquier intervalo de 15S</span><span class="sxs-lookup"><span data-stu-id="5afaa-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="5afaa-130">**Vibración de llegada entre paquetes**</span><span class="sxs-lookup"><span data-stu-id="5afaa-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="5afaa-131"><30ms durante cualquier intervalo de 15S</span><span class="sxs-lookup"><span data-stu-id="5afaa-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="5afaa-132"><15ms durante cualquier intervalo de 15S</span><span class="sxs-lookup"><span data-stu-id="5afaa-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="5afaa-133">**Reordenación de paquetes**</span><span class="sxs-lookup"><span data-stu-id="5afaa-133">**Packet reorder**</span></span>    |<span data-ttu-id="5afaa-134"><% 0,05% de paquetes fuera de servicio</span><span class="sxs-lookup"><span data-stu-id="5afaa-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="5afaa-135"><% 0,01% de paquetes fuera de servicio</span><span class="sxs-lookup"><span data-stu-id="5afaa-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="5afaa-136">\*El objetivo de la métrica de latencia supone que el sitio o los sitios de la empresa y los bordes de Microsoft están en el mismo continente.</span><span class="sxs-lookup"><span data-stu-id="5afaa-136">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="5afaa-137">La conexión del sitio de su empresa con el perímetro de la red de Microsoft incluye acceso de red de primer salto, que puede ser WiFi u otra tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="5afaa-137">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="5afaa-138">Los objetivos de rendimiento de red suponen un ancho de banda adecuado o un [plan QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-138">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="5afaa-139">En otras palabras, los requisitos se aplican directamente al tráfico de medios en tiempo real de Teams cuando la conexión de red está por debajo de una carga máxima.</span><span class="sxs-lookup"><span data-stu-id="5afaa-139">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="5afaa-140">Para obtener más ayuda con la preparación de la red para Teams, consulte [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span><span class="sxs-lookup"><span data-stu-id="5afaa-140">For more help with preparing your network for Teams, check out [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="5afaa-141">Requisitos de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="5afaa-141">Bandwidth requirements</span></span>
<span data-ttu-id="5afaa-142">Microsoft Teams te ofrece la mejor experiencia de audio, vídeo y uso compartido de contenido, independientemente de las condiciones de tu red.</span><span class="sxs-lookup"><span data-stu-id="5afaa-142">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="5afaa-143">Con los códecs variables, los medios se pueden negociar en entornos de ancho de banda limitados con un impacto mínimo.</span><span class="sxs-lookup"><span data-stu-id="5afaa-143">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="5afaa-144">Pero donde el ancho de banda no es un problema, las experiencias se pueden optimizar para la calidad, incluida la resolución de video de 1080p, hasta 30 fps para video y 15fps para el contenido y el audio de alta fidelidad.</span><span class="sxs-lookup"><span data-stu-id="5afaa-144">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="5afaa-145">Otras consideraciones sobre la red</span><span class="sxs-lookup"><span data-stu-id="5afaa-145">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="5afaa-146">Resolución de nombres externos</span><span class="sxs-lookup"><span data-stu-id="5afaa-146">External Name Resolution</span></span>

<span data-ttu-id="5afaa-147">Asegúrese de que todos los equipos cliente que ejecutan el cliente de Teams puedan resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365 y que los firewalls no impiden el acceso.</span><span class="sxs-lookup"><span data-stu-id="5afaa-147">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="5afaa-148">Para obtener información sobre cómo configurar puertos de firewall, vaya a [Office 365 URL e intervalos IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-148">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="5afaa-149">Tamaño del grupo NAT</span><span class="sxs-lookup"><span data-stu-id="5afaa-149">NAT Pool Size</span></span>

<span data-ttu-id="5afaa-150">Cuando varios usuarios o dispositivos obtienen acceso a Office 365 mediante la traducción de direcciones de red (NAT) o la traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos que se encuentran detrás de cada dirección IP enrutable pública no superen el número admitido.</span><span class="sxs-lookup"><span data-stu-id="5afaa-150">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="5afaa-151">Para mitigar este riesgo, asegúrese de que se asignan direcciones IP públicas adecuadas a los grupos NAT para evitar el agotamiento del puerto.</span><span class="sxs-lookup"><span data-stu-id="5afaa-151">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="5afaa-152">El agotamiento del puerto provocará problemas a los usuarios finales internos y los dispositivos al conectarse a los servicios 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="5afaa-152">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="5afaa-153">Para obtener más información, consulte [compatibilidad de NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="5afaa-153">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="5afaa-154">**Guía de detección y prevención de intrusiones**</span><span class="sxs-lookup"><span data-stu-id="5afaa-154">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="5afaa-155">Si su entorno tiene un sistema de detección o prevención de intrusiones (IDS/IPS) implementado para una capa adicional de seguridad para conexiones salientes, asegúrese de que todo el tráfico con destino a las direcciones URL de Office 365 se encuentra en la lista blanca.</span><span class="sxs-lookup"><span data-stu-id="5afaa-155">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="5afaa-156">Determinación del estado de la red</span><span class="sxs-lookup"><span data-stu-id="5afaa-156">Network health determination</span></span>
-----------------

<span data-ttu-id="5afaa-157">Al planear la implementación de Microsoft Teams en su red, debe asegurarse de que tiene el ancho de banda necesario, que tiene acceso a todas las direcciones IP requeridas, que se han abierto los puertos correctos y que está cumpliendo los requisitos de rendimiento para los medios en tiempo real .</span><span class="sxs-lookup"><span data-stu-id="5afaa-157">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="5afaa-158">Si sabe que no cumplirá estos criterios, los usuarios finales no obtendrán una experiencia óptima de Teams debido a la mala calidad de las llamadas y las reuniones.</span><span class="sxs-lookup"><span data-stu-id="5afaa-158">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="5afaa-159">Si no cumple estos criterios, es el momento de considerar pausar el proyecto para asegurarse de que cumple los criterios antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5afaa-159">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="5afaa-161">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="5afaa-161">Decision Point</span></span>         |<span data-ttu-id="5afaa-162">¿Ha evaluado sus capacidades de red para admitir medios en tiempo real?</span><span class="sxs-lookup"><span data-stu-id="5afaa-162">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="5afaa-163">Si su red no se ha evaluado correctamente o sabe que no es compatible con los medios en tiempo real, deshabilitará las funciones de vídeo y pantalla compartida para reducir el impacto de la red y las experiencias de equipos deficientes.</span><span class="sxs-lookup"><span data-stu-id="5afaa-163">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Un icono que representa los pasos siguientes](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="5afaa-165">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="5afaa-165">Next Steps</span></span>         |<span data-ttu-id="5afaa-166">Calidad de red desconocida: realice una evaluación de la disponibilidad de red para determinar si su red está lista para los medios en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="5afaa-166">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="5afaa-167">Calidad de red deficiente: realice los pasos de corrección de red para proporcionar un entorno adecuado para los medios en tiempo real de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="5afaa-167">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="5afaa-168">Red satisfactoria: Asegúrese de que todas las direcciones IP y los puertos son accesibles correctamente.</span><span class="sxs-lookup"><span data-stu-id="5afaa-168">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="5afaa-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5afaa-169">Related Topics</span></span>

[<span data-ttu-id="5afaa-170">Vídeo: planificación de red</span><span class="sxs-lookup"><span data-stu-id="5afaa-170">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
