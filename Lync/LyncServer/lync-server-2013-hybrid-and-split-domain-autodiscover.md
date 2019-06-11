---
title: 'Lync Server 2013: híbrida y dividida-dominio-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389288a695f7e8ed96ab72d16f612ffd92a7b013
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="7dd1b-102">Híbrida y dividida en dominios: detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dd1b-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dd1b-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="7dd1b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="7dd1b-104">Un espacio de direcciones SIP compartido, también conocido como implementación de *dominios divididos* o una implementación *híbrida* , es una configuración en la que los usuarios se implementan en una implementación local y en un entorno en línea.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="7dd1b-105">El resultado deseado es tener un usuario, independientemente de dónde se encuentre su servidor principal (local o en línea), iniciar sesión en la implementación y ser redirigido a la ubicación del servidor local.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="7dd1b-106">Para ello, se usa la característica de detección automática de Lync Server 2013 para redirigir el usuario en línea a la topología de conexión.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="7dd1b-107">Para ello, configure el localizador de recursos uniforme (URL) de detección automática mediante el shell de administración de Lync Server, el cmdlet **Get-CsHostingProvider** y el cmdlet **set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="7dd1b-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="7dd1b-108">Movilidad para la implementación de dominios divididos</span><span class="sxs-lookup"><span data-stu-id="7dd1b-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="7dd1b-109">Tendrá que recopilar y registrar los siguientes atributos implementados:</span><span class="sxs-lookup"><span data-stu-id="7dd1b-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="7dd1b-110">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="7dd1b-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="7dd1b-111">En los resultados, busque el proveedor en línea con el atributo **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="7dd1b-112">Por ejemplo, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="7dd1b-113">Registre el valor de la ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="7dd1b-114">Habilitar la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="7dd1b-115">Habilitar la Federación para el proveedor en línea.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-115">Enable federation for the online provider.</span></span> <span data-ttu-id="7dd1b-116">De forma predeterminada, todos los usuarios conectados están habilitados para la Federación de dominios y pueden comunicarse con todos los dominios.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="7dd1b-117">Si va a definir dominios bloqueados y permitidos, determine los dominios que va a permitir o bloquear de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="7dd1b-118">Para la Federación en línea, debe planear las excepciones del firewall, los certificados y los registros de host DNS (A o AAAA, si usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="7dd1b-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="7dd1b-119">Además, debe configurar directivas de Federación.</span><span class="sxs-lookup"><span data-stu-id="7dd1b-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="7dd1b-120">Para obtener información detallada, consulte [planificación de Lync server 2013 y Federación de Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="7dd1b-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

