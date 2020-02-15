---
title: 'Lync Server 2013: Planeación de la conectividad con RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f69e8286e341b7769a58d03c42d0a43e63075
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="3552d-102">Planeación de la conectividad con RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3552d-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3552d-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3552d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3552d-104">Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="3552d-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="3552d-105">Los usuarios que realicen y reciban llamadas no deben tener en cuenta la tecnología subyacente: desde el punto de vista del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC deberían parecer sólo otra llamada telefónica.</span><span class="sxs-lookup"><span data-stu-id="3552d-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="3552d-106">Lync Server 2013 proporciona conectividad con RTC confiable y escalable mediante las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3552d-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="3552d-107">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="3552d-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="3552d-108">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="3552d-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="3552d-109">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="3552d-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="3552d-110">Según el tamaño, la cobertura geográfica y la infraestructura de voz existente, una empresa puede usar una, dos o incluso las tres opciones en varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="3552d-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3552d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3552d-111">In This Section</span></span>

  - [<span data-ttu-id="3552d-112">Enlace troncal SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3552d-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="3552d-113">Conexiones SIP directas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3552d-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="3552d-114">M:N troncal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3552d-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="3552d-115">Reglas de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3552d-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="3552d-116">Planeación del enrutamiento de voz saliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3552d-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

