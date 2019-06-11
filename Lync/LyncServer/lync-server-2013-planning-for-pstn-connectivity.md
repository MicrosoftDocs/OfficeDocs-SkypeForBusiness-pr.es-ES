---
title: 'Lync Server 2013: planificación de la conectividad RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64089661b5d185362a8e47128e9a890b03edfd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="54908-102">Planificación de la conectividad RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54908-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54908-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="54908-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="54908-104">Una solución VoIP empresarial necesita proporcionar llamadas entrantes y salientes a la red telefónica conmutada (RTC) sin que la calidad de servicio (QoS) se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="54908-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="54908-105">Los usuarios que realicen y reciban llamadas no deben ser conscientes de la tecnología subyacente: desde el punto de vista del usuario, una llamada entre la infraestructura de telefonía IP empresarial y la RTC debe parecer simplemente otra llamada telefónica.</span><span class="sxs-lookup"><span data-stu-id="54908-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="54908-106">Lync Server 2013 proporciona conectividad RTC confiable y escalable con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="54908-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="54908-107">**Troncos SIP** a un proveedor de servicios de telefonía por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="54908-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="54908-108">**Conexiones SIP directas** a una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="54908-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="54908-109">**Conexiones SIP directas** a una PBX</span><span class="sxs-lookup"><span data-stu-id="54908-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="54908-110">Según cuál sea el tamaño, la cobertura geográfica y la infraestructura de voz existente de una organización, es posible usar una, dos o todas estas opciones en diversas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="54908-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54908-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="54908-111">In This Section</span></span>

  - [<span data-ttu-id="54908-112">Troncalización SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54908-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="54908-113">Conexiones SIP directas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54908-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="54908-114">M:N troncal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54908-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="54908-115">Reglas de traducción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54908-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="54908-116">Planeación del enrutamiento de voz saliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54908-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

