---
title: 'Lync Server 2013: híbrido y dividido-dominio-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e4adc6c0f8a3ffda53821c412e0efbda74bbebc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="e6446-102">Híbrido y dividido-dominio-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6446-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6446-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="e6446-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="e6446-104">Un espacio de direcciones SIP compartido, también conocido como implementación de *dominio dividido* o implementación *híbrida* , es una configuración en la que los usuarios se implementan en una implementación local y en un entorno en línea.</span><span class="sxs-lookup"><span data-stu-id="e6446-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="e6446-105">El resultado deseado es tener a un usuario, independientemente de dónde se encuentre el servidor principal (local o en línea), iniciar sesión en la implementación y ser redireccionado a la ubicación del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="e6446-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="e6446-106">Para ello, se usa la característica de detección automática de Lync Server 2013 para redirigir el usuario en línea a la topología en línea.</span><span class="sxs-lookup"><span data-stu-id="e6446-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="e6446-107">Para ello, configure el localizador uniforme de recursos (URL) de detección automática mediante el shell de administración de Lync Server, el cmdlet **Get-CsHostingProvider** y el cmdlet **set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="e6446-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="e6446-108">Movilidad para la implementación de dominio dividido</span><span class="sxs-lookup"><span data-stu-id="e6446-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="e6446-109">Necesitará recopilar y registrar los siguientes atributos implementados:</span><span class="sxs-lookup"><span data-stu-id="e6446-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="e6446-110">Desde el shell de administración de Lync Server, escriba</span><span class="sxs-lookup"><span data-stu-id="e6446-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="e6446-111">En los resultados, encuentre el proveedor en línea que tenga el atributo **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="e6446-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="e6446-112">Por ejemplo, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6446-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="e6446-113">Registre el valor de ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="e6446-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="e6446-114">Habilite la Federación en el panel de control de Lync Server local, lo que permite la Federación con el proveedor en línea.</span><span class="sxs-lookup"><span data-stu-id="e6446-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="e6446-115">Habilite la federación para el proveedor en línea.</span><span class="sxs-lookup"><span data-stu-id="e6446-115">Enable federation for the online provider.</span></span> <span data-ttu-id="e6446-116">De forma predeterminada, todos los usuarios en línea están habilitados para la Federación de dominios y pueden comunicarse con todos los dominios.</span><span class="sxs-lookup"><span data-stu-id="e6446-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="e6446-117">Si va a definir dominios bloqueados y permitidos, determine los dominios que se permitirán o se bloquearán explícitamente.</span><span class="sxs-lookup"><span data-stu-id="e6446-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="e6446-118">Para la Federación en línea, debe planear las excepciones del firewall, los certificados y los registros de host DNS (A o AAAA, si usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="e6446-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="e6446-119">Asimismo, debe configurar las directivas de federación.</span><span class="sxs-lookup"><span data-stu-id="e6446-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="e6446-120">Para obtener más información, consulte [Planning for Lync Server 2013 y Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="e6446-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

