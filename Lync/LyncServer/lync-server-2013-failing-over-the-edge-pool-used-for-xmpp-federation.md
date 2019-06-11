---
title: 'Lync Server 2013: Conmutación por error para el grupo de servidores perimetrales para la federación XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="d44be-102">Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d44be-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d44be-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d44be-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d44be-104">En su organización, hay un grupo perimetral designado como grupo para usar en la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="d44be-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="d44be-105">Si este grupo deja de funcionar, debe conmutar por error la Federación XMPP para usar un grupo de servidores perimetrales diferente antes de que la Federación XMPP pueda volver a funcionar.</span><span class="sxs-lookup"><span data-stu-id="d44be-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="d44be-106">La primera vez que instala agrupaciones de límites y habilita la Federación de XMPP, puede simplificar el proceso de recuperación ante desastres configurando registros SRV de DNS para todos los grupos de borde para la Federación de XMPP, en lugar de solo uno.</span><span class="sxs-lookup"><span data-stu-id="d44be-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="d44be-107">Cada uno de estos registros SRV debe tener un conjunto de prioridades diferente.</span><span class="sxs-lookup"><span data-stu-id="d44be-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="d44be-108">Todo el tráfico de Federación XMPP pasa por el grupo con el registro SRV con la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="d44be-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="d44be-109">Para obtener más información sobre cómo habilitar y configurar la Federación XMPP, consulte [configurar la Federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="d44be-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="d44be-110">En el procedimiento siguiente, EdgePool1 es el grupo que originalmente contenía la Federación de XMPP y EdgePool2 es el grupo que ahora hospedará la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="d44be-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="d44be-111">Error en el grupo perimetral usado para la Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="d44be-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="d44be-112">Si aún no tiene otra agrupación perimetral implementada (aparte de la que actualmente está desactivada), implemente ese grupo.</span><span class="sxs-lookup"><span data-stu-id="d44be-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="d44be-113">Para obtener más información, consulte [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d44be-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="d44be-114">En cada servidor perimetral en el nuevo grupo de límites que ahora hospede la Federación XMPP (EdgePool2), ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d44be-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="d44be-115">Ejecute el cmdlet siguiente para redirigir la ruta de Federación de XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="d44be-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="d44be-116">En este ejemplo, Site2 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="d44be-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="d44be-117">En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d44be-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="d44be-118">Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d44be-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="d44be-119">Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="d44be-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="d44be-120">Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.</span><span class="sxs-lookup"><span data-stu-id="d44be-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="d44be-121">Inicie los servicios en todos los servidores perimetrales del grupo perimetral que ahora hospedarán la Federación de XMPP:</span><span class="sxs-lookup"><span data-stu-id="d44be-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

