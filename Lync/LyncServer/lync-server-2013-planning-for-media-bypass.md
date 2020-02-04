---
title: 'Lync Server 2013: Planificar la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="67d1c-102">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67d1c-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="67d1c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="67d1c-104">La omisión de elementos multimedia hace referencia a quitar el servidor de mediación de la ruta multimedia siempre que sea posible para las llamadas cuya señalización atraviese el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="67d1c-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="67d1c-105">La omisión de medios puede mejorar la calidad de la voz al reducir la latencia, la conversión innecesaria, la posibilidad de la pérdida de paquetes y la cantidad de puntos de errores potenciales.</span><span class="sxs-lookup"><span data-stu-id="67d1c-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="67d1c-106">La escalabilidad puede mejorarse, ya que la eliminación del procesamiento de medios para llamadas omitidas reduce la carga en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="67d1c-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="67d1c-107">Esta reducción de carga complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="67d1c-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="67d1c-108">Cuando un sitio de sucursal sin un servidor de mediación se conecta a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios disminuye el requisito de ancho de banda permitiendo que los medios de un cliente de un sitio de sucursal fluyan directamente a su puerta de enlace local sin en primer lugar, debe transmitirse a través del vínculo WAN a un servidor de mediación del sitio central y viceversa.</span><span class="sxs-lookup"><span data-stu-id="67d1c-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="67d1c-109">Al aliviar el servidor de mediación del procesamiento multimedia, la omisión de medios también puede reducir el número de servidores de mediación que requiere una infraestructura de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="67d1c-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="67d1c-110">La siguiente figura muestra las rutas de señalización y los medios básicos en las topologías con omisión de medios y sin ella.</span><span class="sxs-lookup"><span data-stu-id="67d1c-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="67d1c-111">**Rutas de señalización y medios con omisión de medios y sin ella**</span><span class="sxs-lookup"><span data-stu-id="67d1c-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="67d1c-112">![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz")</span><span class="sxs-lookup"><span data-stu-id="67d1c-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="67d1c-113">Como regla general, habilita la omisión de medios siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="67d1c-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="67d1c-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="67d1c-114">In This Section</span></span>

  - [<span data-ttu-id="67d1c-115">Información general sobre la omisión de elementos multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="67d1c-116">Modos de omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="67d1c-117">Omisión de medios y control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="67d1c-118">Requisitos técnicos para la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="67d1c-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="67d1c-119">Related Sections</span></span>

[<span data-ttu-id="67d1c-120">Implementación de características avanzadas de telefonía empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67d1c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="67d1c-121">See Also</span></span>


[<span data-ttu-id="67d1c-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="67d1c-123">Opciones de omisión de multimedia global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d1c-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

