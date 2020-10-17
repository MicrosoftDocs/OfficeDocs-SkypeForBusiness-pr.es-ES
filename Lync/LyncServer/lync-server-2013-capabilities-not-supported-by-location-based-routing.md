---
title: 'Lync Server 2013: capacidades no compatibles con el enrutamiento de Location-Based'
description: 'Lync Server 2013: capacidades no compatibles con el enrutamiento de Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf9cd03a8cbdd50e136605c4f172598b2ad3f523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565166"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7e33c-103">Capacidades no compatibles con el enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e33c-103">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e33c-104">_**Última modificación del tema:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="7e33c-104">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="7e33c-105">El enrutamiento Location-Based no se aplica a los siguientes tipos de interacciones.</span><span class="sxs-lookup"><span data-stu-id="7e33c-105">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="7e33c-106">Location-Based el enrutamiento no se aplica cuando los extremos de Lync interactúan con los extremos RTC mediante estas funciones.</span><span class="sxs-lookup"><span data-stu-id="7e33c-106">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="7e33c-107">Acceso telefónico a conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="7e33c-107">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="7e33c-108">Llamadas RTC entrantes y salientes a través del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="7e33c-108">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="7e33c-109">Estacionamiento de llamadas o recuperación de llamadas RTC a través del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="7e33c-109">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="7e33c-110">Llamadas RTC entrantes al servicio de anuncios</span><span class="sxs-lookup"><span data-stu-id="7e33c-110">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="7e33c-111">Llamadas RTC entrantes recuperadas a través de la atención de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="7e33c-111">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="7e33c-112">Para aplicar Location-Based reglas de enrutamiento a los tipos de interacciones de la lista siguiente, debe habilitar el enrutamiento de Location-Based para las conferencias:</span><span class="sxs-lookup"><span data-stu-id="7e33c-112">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="7e33c-113">Acceso telefónico PSTN desde conferencias</span><span class="sxs-lookup"><span data-stu-id="7e33c-113">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="7e33c-114">Escalaciones de conversaciones de audio punto a punto a conferencias en las que intervienen extremos RTC</span><span class="sxs-lookup"><span data-stu-id="7e33c-114">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="7e33c-115">Transferencias de consulta que implican extremos de RTC</span><span class="sxs-lookup"><span data-stu-id="7e33c-115">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="7e33c-116">Para habilitar el enrutamiento de Location-Based para conferencias, consulte [enrutamiento basado en ubicación para conferencias en Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="7e33c-116">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7e33c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e33c-117">See Also</span></span>


[<span data-ttu-id="7e33c-118">Planeación del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e33c-118">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

