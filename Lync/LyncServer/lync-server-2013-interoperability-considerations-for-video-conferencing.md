---
title: 'Lync Server 2013: consideraciones sobre la interoperabilidad para conferencias de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a061a87ee3c386160f9b94053d82d4ac05812f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="be90e-102">Consideraciones sobre interoperabilidad para la Conferencia de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be90e-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be90e-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="be90e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="be90e-104">En esta sección se describe la experiencia del usuario durante la fase de coexistencia de la migración, cuando hay interoperabilidad entre clientes heredados y un grupo de servidores de Lync Server 2013 o clientes de Lync Server 2013 y un grupo de servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="be90e-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="be90e-105">Grupos de servidores 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="be90e-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="be90e-106">Los usuarios experimentarán el siguiente comportamiento cuando se use un cliente heredado en un grupo de servidores de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="be90e-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="be90e-107">Para llamadas de dos participantes, la resolución de vídeo es la misma que en el grupo de servidores heredado.</span><span class="sxs-lookup"><span data-stu-id="be90e-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="be90e-p101">Para conferencias de varios participantes, las características de resolución de vídeo y conferencia de vídeo son las mismas que en el grupo de servidores heredado. La vista de galería y la alta resolución no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="be90e-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="be90e-110">Grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="be90e-110">Legacy Pools</span></span>

<span data-ttu-id="be90e-111">Los usuarios experimentarán el siguiente comportamiento cuando se use un cliente de Lync Server 2013 en un grupo de servidores heredados:</span><span class="sxs-lookup"><span data-stu-id="be90e-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="be90e-112">Para llamadas de dos participantes, los clientes de Lync Server 2013 pueden usar nuevas características de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be90e-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="be90e-113">H. 264 está disponible si ambos participantes usan clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be90e-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="be90e-114">El cliente de Lync Server 2013 usa el valor predeterminado para TotalReceiveVideoBitRateKb, ya que el servidor heredado no envía esta información con aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="be90e-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="be90e-115">Para conferencias de varios participantes, las características de resolución de vídeo y conferencia de vídeo son las mismas que las que tiene un cliente heredado en el grupo de servidores heredado.</span><span class="sxs-lookup"><span data-stu-id="be90e-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be90e-116">Cuando un servidor heredado hospeda un cliente de Lync Server 2013, es posible configurar el ancho de banda de la Conferencia de vídeo para que todos los usuarios del grupo reciban solo vídeo de baja resolución, pero que envíen vídeo de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="be90e-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="be90e-117">Un ejemplo de esto es cuando MaxVideoRateAllowed se establece en CIF-250K en la configuración multimedia y VideoBitRateKb se establece en 2000 kbps en la directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="be90e-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="be90e-118">El efecto neto en esta situación es que la resolución alta no es posible para usuarios del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="be90e-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="be90e-119">Debido a que MaxVideoRateAllowed ya no se usa para los clientes de Lync Server 2013, no puede impedir que los clientes de Lync Server 2013 soliciten vídeo de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="be90e-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="be90e-120">En su lugar, establezca VideoBitRateKb en la directiva de conferencia para todos los usuarios del grupo de servidores al mismo valor que MaxVideoRateAllowed (es decir, CIF se establece en 250 kbps, o VGA se establece en 600 kbps, o HD se establece en 1500 kbps).</span><span class="sxs-lookup"><span data-stu-id="be90e-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

