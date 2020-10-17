---
title: 'Lync Server 2013: conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP'
description: 'Lync Server 2013: conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccdfe119258b4d09ddedefb22d0272d72003bf04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554906"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="ef793-103">Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef793-103">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef793-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ef793-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ef793-p101">En su organización, hay un grupo perimetral designada como el grupo para la federación XMPP. Si este grupo se desactiva, debe conmutar por error la federación XMPP para que use otro grupo perimetral antes de que la federación XMPP pueda volver a trabajar.</span><span class="sxs-lookup"><span data-stu-id="ef793-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="ef793-107">Al instalar primero los grupos perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres estableciendo registros SRV de DNS externos para todos los grupos perimetrales para la federación XMPP, en lugar de solo uno.</span><span class="sxs-lookup"><span data-stu-id="ef793-107">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="ef793-108">Cada uno de estos registros SRV debe tener establecida una prioridad diferente.</span><span class="sxs-lookup"><span data-stu-id="ef793-108">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="ef793-109">Todo el tráfico de la federación XMPP atraviesa el grupo con el registro SRV con la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="ef793-109">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="ef793-110">Para obtener más información sobre cómo habilitar y configurar la Federación XMPP, consulte Configuración de la [Federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="ef793-110">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="ef793-111">En el procedimiento siguiente, EdgePool1 es el grupo que originalmente alojó la federación XMPP y EdgePool2 es el grupo que alojará ahora la federación de XMPP.</span><span class="sxs-lookup"><span data-stu-id="ef793-111">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="ef793-112">Conmutación por error del grupo perimetral usado para la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="ef793-112">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="ef793-113">Si no tiene implementado otro grupo perimetral (además del que está desactivado), implemente dicha grupo.</span><span class="sxs-lookup"><span data-stu-id="ef793-113">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="ef793-114">Para obtener más información, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ef793-114">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="ef793-115">En cada servidor perimetral del nuevo grupo perimetral que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ef793-115">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="ef793-116">Ejecute el siguiente cmdlet para cambiar la ruta de la federación XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="ef793-116">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="ef793-117">En este ejemplo, Site2 es el sitio que contiene el grupo perimetral que alojará ahora la federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral del grupo.</span><span class="sxs-lookup"><span data-stu-id="ef793-117">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="ef793-118">En el servidor DNS externo, cambie el registro de DNS A de la federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ef793-118">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="ef793-p104">Si aún no tiene un registro SRV de DNS para la federación XMPP que resuelva al grupo perimetral que alojará ahora la federación de XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="ef793-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="ef793-121">Compruebe que el grupo perimetral que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.</span><span class="sxs-lookup"><span data-stu-id="ef793-121">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="ef793-122">Inicie los servicios en todos los servidores perimetrales del grupo perimetral que alojará ahora la federación XMPP:</span><span class="sxs-lookup"><span data-stu-id="ef793-122">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

