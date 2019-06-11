---
title: 'Lync Server 2013: consideraciones de interoperabilidad para videoconferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="9be27-102">Consideraciones de interoperabilidad para videoconferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9be27-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be27-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9be27-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9be27-104">En esta sección se describe la experiencia del usuario durante la fase de coexistencia de la migración, cuando hay interoperabilidad entre clientes heredados y un grupo de servidores de Lync Server 2013 o clientes de Lync Server 2013 y un grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="9be27-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="9be27-105">Grupos de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9be27-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="9be27-106">Los usuarios experimentarán el comportamiento siguiente cuando se use un cliente heredado en un grupo de servidores de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9be27-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="9be27-107">Para las llamadas de dos participantes, la resolución de video es la misma que la del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="9be27-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="9be27-108">Para las conferencias de varias partes, la resolución de video y las características de las videoconferencias son las mismas que en el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="9be27-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="9be27-109">La vista de galería y la alta resolución no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9be27-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="9be27-110">Grupos heredados</span><span class="sxs-lookup"><span data-stu-id="9be27-110">Legacy Pools</span></span>

<span data-ttu-id="9be27-111">Los usuarios experimentarán el comportamiento siguiente cuando se use un cliente de Lync Server 2013 en una agrupación heredada:</span><span class="sxs-lookup"><span data-stu-id="9be27-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="9be27-112">Para las llamadas de dos participantes, los clientes de Lync Server 2013 pueden usar las nuevas características de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9be27-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="9be27-113">H. 264 está disponible si ambos participantes usan clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9be27-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="9be27-114">El cliente de Lync Server 2013 usa el valor predeterminado para TotalReceiveVideoBitRateKb, ya que el servidor heredado no envía esta información con aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="9be27-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="9be27-115">Para las conferencias de varias partes, las características de videoconferencias y la resolución de video son las mismas que experimenta un cliente heredado en el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="9be27-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9be27-116">Cuando un servidor heredado hospeda un cliente de Lync Server 2013, es posible configurar ancho de banda de videoconferencias para que todos los usuarios del grupo reciban solo vídeo de baja resolución, pero que envíen video de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="9be27-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="9be27-117">Un ejemplo de ello es cuando MaxVideoRateAllowed se establece en CIF-250K en la configuración de multimedia y VideoBitRateKb se establece en 2000 kbps en la Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9be27-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="9be27-118">El efecto neto en esta situación es que no es posible que los usuarios del grupo tengan una alta resolución.</span><span class="sxs-lookup"><span data-stu-id="9be27-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="9be27-119">Como MaxVideoRateAllowed ya no se usa para los clientes de Lync Server 2013, no puede impedir que los clientes de Lync Server 2013 soliciten video de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="9be27-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="9be27-120">En su lugar, establezca VideoBitRateKb en la Directiva de conferencia para todos los usuarios del grupo al mismo valor que MaxVideoRateAllowed (es decir, CIF se establece en 250 kbps o VGA se establece en 600 Kbps, o HD se establece en 1500 kbps).</span><span class="sxs-lookup"><span data-stu-id="9be27-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

