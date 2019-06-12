---
title: Comprobar la información de la topología
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="cb7be-102">Comprobar la información de la topología</span><span class="sxs-lookup"><span data-stu-id="cb7be-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb7be-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="cb7be-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="cb7be-104">El primer paso para comprobar que la combinación se completó correctamente es ver la información de topología de Office Communications Server 2007 R2 que combinó con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="cb7be-105">En el generador de topologías, el nodo **BackCompatSite** muestra el nombre de dominio completo (FQDN) de cada grupo de servidores de Office Communications Server 2007 R2 y servidor que haya combinado.</span><span class="sxs-lookup"><span data-stu-id="cb7be-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="cb7be-106">Para ver BackCompatSite en el generador de topología</span><span class="sxs-lookup"><span data-stu-id="cb7be-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="cb7be-107">En el entorno de Office Communications Server 2007 R2, abra la herramienta administrativa de Office Communications Server 2007 R2 y anote los FQDN de los grupos y servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="cb7be-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="cb7be-108">En el entorno de Lync Server 2013, abra Topology Builder y, a continuación, expanda el nodo **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="cb7be-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="cb7be-109">Compruebe que se muestran los FQDN de los grupos de servidores y los servidores que combina.</span><span class="sxs-lookup"><span data-stu-id="cb7be-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb7be-110">No verá ninguna información en <STRONG>BackCompatSite</STRONG> para los roles de servidor que se colocan en un servidor front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cb7be-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="cb7be-111">Solo se muestran los roles de servidor necesarios para la interoperabilidad entre Office Communications Server 2007 R2 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="cb7be-112">![Cuadro de diálogo BackCompatSite del generador de topología] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Cuadro de diálogo BackCompatSite del generador de topología")</span><span class="sxs-lookup"><span data-stu-id="cb7be-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="cb7be-113">También puede usar el panel de control de Lync Server 2013 para ver la topología combinada.</span><span class="sxs-lookup"><span data-stu-id="cb7be-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="cb7be-114">En el panel de control de Lync Server 2013, puede ver cada FQDN del servidor, FQDN del grupo y nombre del sitio de la topología de la combinación.</span><span class="sxs-lookup"><span data-stu-id="cb7be-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="cb7be-115">Los servidores combinados tienen un nombre de **sitio** de **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="cb7be-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="cb7be-116">Para ver la topología combinada en el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb7be-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="cb7be-117">Abra el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="cb7be-118">Haga clic en **topología**.</span><span class="sxs-lookup"><span data-stu-id="cb7be-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="cb7be-119">En la pestaña **Estado** , compruebe que los servidores y las agrupaciones que ha combinado aparecen en la columna **sitio** de **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="cb7be-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="cb7be-120">![Panel de control de Lync Server que muestra una topología combinada] (images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panel de control de Lync Server que muestra una topología combinada")</span><span class="sxs-lookup"><span data-stu-id="cb7be-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="cb7be-121">Para ver más detalles sobre una agrupación combinada, use el cmdlet **Get-CsPool** .</span><span class="sxs-lookup"><span data-stu-id="cb7be-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="cb7be-122">Además de la información que está disponible en el generador de topología y el panel de control de Lync Server 2013, este cmdlet muestra los servicios que se ejecutan en el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb7be-123">Al publicar la topología después de ejecutar el Asistente de combinación en el generador de topología, los directorios de conferencia se combinan con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="cb7be-124">Los directorios de conferencia se pueden comprobar ejecutando el cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="cb7be-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="cb7be-125">Para ver los servicios de un grupo combinado</span><span class="sxs-lookup"><span data-stu-id="cb7be-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="cb7be-126">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="cb7be-127">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="cb7be-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="cb7be-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb7be-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="cb7be-129">Para comprobar los directorios de las conferencias combinados</span><span class="sxs-lookup"><span data-stu-id="cb7be-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="cb7be-130">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="cb7be-131">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="cb7be-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="cb7be-132">Compruebe que todos los directorios de conferencia para el grupo de servidores o el servidor que está combinando estén ahora en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb7be-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

