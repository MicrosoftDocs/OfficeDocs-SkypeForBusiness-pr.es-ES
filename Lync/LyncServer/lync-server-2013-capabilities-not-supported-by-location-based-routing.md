---
title: 'Lync Server 2013: capacidades no compatibles con el enrutamiento basado en ubicación'
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
ms.openlocfilehash: ff96f72ff7d71c005f97142ed9844b7c9509e022
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f3a94-102">Capacidades no compatibles con el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3a94-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3a94-103">_**Última modificación del tema:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="f3a94-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="f3a94-104">El enrutamiento basado en ubicación no se aplica a los siguientes tipos de interacciones.</span><span class="sxs-lookup"><span data-stu-id="f3a94-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="f3a94-105">El enrutamiento basado en ubicación no se aplica cuando los puntos de conexión de Lync interactúan con extremos RTC mediante estas funciones.</span><span class="sxs-lookup"><span data-stu-id="f3a94-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="f3a94-106">Acceso telefónico a conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="f3a94-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="f3a94-107">Llamadas RTC entrantes y salientes a través del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3a94-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="f3a94-108">Estacionamiento de llamadas o recuperación de llamadas RTC a través del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="f3a94-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="f3a94-109">Llamadas RTC entrantes al servicio de anuncios</span><span class="sxs-lookup"><span data-stu-id="f3a94-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="f3a94-110">Llamadas RTC entrantes recuperadas a través de la atención de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="f3a94-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="f3a94-111">Para aplicar reglas de enrutamiento basadas en la ubicación a los tipos de interacciones de la lista siguiente, debe habilitar el enrutamiento basado en ubicación para las conferencias:</span><span class="sxs-lookup"><span data-stu-id="f3a94-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="f3a94-112">Acceso telefónico PSTN desde conferencias</span><span class="sxs-lookup"><span data-stu-id="f3a94-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="f3a94-113">Escalaciones de conversaciones de audio punto a punto a conferencias en las que intervienen extremos RTC</span><span class="sxs-lookup"><span data-stu-id="f3a94-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="f3a94-114">Transferencias de consulta que implican extremos de RTC</span><span class="sxs-lookup"><span data-stu-id="f3a94-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="f3a94-115">Para habilitar el enrutamiento basado en ubicación para las conferencias, consulte [enrutamiento basado en ubicación para conferencias en Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="f3a94-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f3a94-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3a94-116">See Also</span></span>


[<span data-ttu-id="f3a94-117">Planeación del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3a94-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

