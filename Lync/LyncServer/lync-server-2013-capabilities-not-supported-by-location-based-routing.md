---
title: 'Lync Server 2013: Capacidades no compatibles con el enrutamiento basado en ubicación'
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
ms.openlocfilehash: 967b5b7388ce60eafd46791c226bf1a3edbe0c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="9e093-102">Capacidades no compatibles con el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e093-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e093-103">_**Última modificación del tema:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="9e093-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="9e093-104">El enrutamiento basado en la ubicación no se aplica a los siguientes tipos de interacciones.</span><span class="sxs-lookup"><span data-stu-id="9e093-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="9e093-105">El enrutamiento basado en la ubicación no se aplica cuando los puntos de conexión de Lync interactúan con puntos de conexión RTC mediante estas características.</span><span class="sxs-lookup"><span data-stu-id="9e093-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="9e093-106">Marcación RTC para conferencias</span><span class="sxs-lookup"><span data-stu-id="9e093-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="9e093-107">Llamadas RTC entrantes y salientes a través del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="9e093-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="9e093-108">Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="9e093-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="9e093-109">Llamadas RTC entrantes al servicio de anuncio</span><span class="sxs-lookup"><span data-stu-id="9e093-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="9e093-110">Llamadas RTC entrantes recuperadas a través de la atención de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="9e093-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="9e093-111">Para aplicar reglas de enrutamiento basadas en la ubicación a los tipos de interacciones de la siguiente lista, debe habilitar el enrutamiento basado en la ubicación para las conferencias:</span><span class="sxs-lookup"><span data-stu-id="9e093-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="9e093-112">Iniciar llamadas RTC desde una conferencia</span><span class="sxs-lookup"><span data-stu-id="9e093-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="9e093-113">Escalaciones desde conversaciones de audio de punto a punto a conferencias en las que participen extremos de RTC</span><span class="sxs-lookup"><span data-stu-id="9e093-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="9e093-114">Transferencias de consulta con extremos de RTC</span><span class="sxs-lookup"><span data-stu-id="9e093-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="9e093-115">Para habilitar el enrutamiento basado en la ubicación de las conferencias, consulte [enrutamiento basado en ubicación para conferencias en Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="9e093-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9e093-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e093-116">See Also</span></span>


[<span data-ttu-id="9e093-117">Planificar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e093-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

