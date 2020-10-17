---
title: 'Lync Server 2013: llamadas salientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a77ddf0757cd463bb8f1b95dbecfe90fd1086c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524407"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="39cf5-102">Llamadas salientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39cf5-102">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39cf5-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="39cf5-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="39cf5-104">El enrutamiento de llamadas salientes de usuarios habilitados para el enrutamiento Location-Based se ve afectado por la ubicación de red del extremo del usuario.</span><span class="sxs-lookup"><span data-stu-id="39cf5-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="39cf5-105">En la tabla siguiente se muestra cómo el enrutamiento de Location-Based afecta al enrutamiento de las llamadas salientes en función de la ubicación del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="39cf5-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="39cf5-106">Autor de la llamada que realiza una llamada saliente a la RTC</span><span class="sxs-lookup"><span data-stu-id="39cf5-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="39cf5-107">Extremo de usuario ubicado en un sitio de red habilitado para el enrutamiento Location-Based</span><span class="sxs-lookup"><span data-stu-id="39cf5-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="39cf5-108">Extremo de usuario ubicado en un sitio de red desconocido o no habilitado para el enrutamiento Location-Based</span><span class="sxs-lookup"><span data-stu-id="39cf5-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39cf5-109">Autorización de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="39cf5-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="39cf5-110">La llamada se autoriza en función de la Directiva de voz del usuario</span><span class="sxs-lookup"><span data-stu-id="39cf5-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="39cf5-111">La llamada se autoriza en función de la Directiva de voz del usuario</span><span class="sxs-lookup"><span data-stu-id="39cf5-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39cf5-112">Enrutamiento de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="39cf5-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="39cf5-113">La llamada se enruta según la Directiva de enrutamiento de voz del sitio de red</span><span class="sxs-lookup"><span data-stu-id="39cf5-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="39cf5-114">La llamada se redirige según la Directiva de voz del usuario y solo a través de troncos no habilitados para Location-Based enrutamiento (si está disponible)</span><span class="sxs-lookup"><span data-stu-id="39cf5-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="39cf5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39cf5-115">See Also</span></span>


[<span data-ttu-id="39cf5-116">Escenarios para Location-Based el enrutamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39cf5-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

