---
title: Comprobación de la información de topología
description: Compruebe la información de la topología.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed41cd95fffdca629e710dcf443631d0c74c69e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555496"
---
# <a name="verify-topology-information"></a><span data-ttu-id="88aaf-103">Comprobación de la información de topología</span><span class="sxs-lookup"><span data-stu-id="88aaf-103">Verify topology information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88aaf-104">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="88aaf-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="88aaf-105">El primer paso para comprobar que la combinación se completó correctamente es ver la información de topología de Office Communications Server 2007 R2 que se combinó con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-105">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="88aaf-106">En el generador de topologías, el nodo **BackCompatSite** muestra el nombre de dominio completo (FQDN) de cada grupo y servidor de Office Communications Server 2007 R2 que ha combinado.</span><span class="sxs-lookup"><span data-stu-id="88aaf-106">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="88aaf-107">Para ver BackCompatSite en el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="88aaf-107">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="88aaf-108">En el entorno de Office Communications Server 2007 R2, abra la herramienta administrativa de Office Communications Server 2007 R2 y observe los FQDN de los servidores y grupos de servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="88aaf-108">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="88aaf-109">En el entorno de Lync Server 2013, abra el generador de topologías y, a continuación, expanda el nodo **BackCompatSite** .</span><span class="sxs-lookup"><span data-stu-id="88aaf-109">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="88aaf-110">Compruebe que se muestren los FQDN de los servidores y grupos de servidores que desea combinar.</span><span class="sxs-lookup"><span data-stu-id="88aaf-110">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88aaf-111">En <STRONG>BackCompatSite</STRONG>, no verá ninguna información sobre roles del servidor instalados en un servidor front-end o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="88aaf-111">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="88aaf-112">Solo se muestran los roles de servidor necesarios para la interoperabilidad entre Office Communications Server 2007 R2 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-112">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="88aaf-113">![Cuadro de diálogo BackCompatSite del generador de topologías](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Cuadro de diálogo BackCompatSite del generador de topologías")</span><span class="sxs-lookup"><span data-stu-id="88aaf-113">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="88aaf-114">También puede usar el panel de control de Lync Server 2013 para ver la topología combinada.</span><span class="sxs-lookup"><span data-stu-id="88aaf-114">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="88aaf-115">En el panel de control de Lync Server 2013, puede ver el FQDN de cada servidor, el FQDN del grupo de servidores y el nombre del sitio de la topología combinada.</span><span class="sxs-lookup"><span data-stu-id="88aaf-115">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="88aaf-116">Los servidores combinados tienen un nombre de **Sitio** de **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="88aaf-116">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="88aaf-117">Para ver la topología combinada en el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88aaf-117">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="88aaf-118">Abra el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-118">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="88aaf-119">Haga clic en **Topología**.</span><span class="sxs-lookup"><span data-stu-id="88aaf-119">Click **Topology**.</span></span>

3.  <span data-ttu-id="88aaf-120">En la pestaña **Estado**, busque **BackCompatSite** en la columna**Sitio** para confirmar que aparecen los servidores y grupos que ha combinado.</span><span class="sxs-lookup"><span data-stu-id="88aaf-120">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="88aaf-121">![Panel de control de Lync Server donde se muestra la topología combinada](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panel de control de Lync Server donde se muestra la topología combinada")</span><span class="sxs-lookup"><span data-stu-id="88aaf-121">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="88aaf-122">Para ver información más detallada sobre un grupo combinado, use el cmdlet **Get-CsPool**.</span><span class="sxs-lookup"><span data-stu-id="88aaf-122">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="88aaf-123">Además de la información disponible en el generador de topologías y el panel de control de Lync Server 2013, este cmdlet muestra los servicios que se ejecutan en el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-123">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88aaf-124">Al publicar la topología después de ejecutar el Asistente de combinación en el generador de topologías, los directorios de conferencia se combinan en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-124">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="88aaf-125">Los directorios de conferencia se pueden comprobar mediante la ejecución del cmdlet <STRONG>Get-CsConferenceDirectory</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="88aaf-125">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="88aaf-126">Para ver los servicios de un grupo combinado</span><span class="sxs-lookup"><span data-stu-id="88aaf-126">To view services on a merged pool</span></span>

1.  <span data-ttu-id="88aaf-127">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-127">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="88aaf-128">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="88aaf-128">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="88aaf-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="88aaf-129">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="88aaf-130">Para comprobar los directorios de conferencia combinados</span><span class="sxs-lookup"><span data-stu-id="88aaf-130">To verify conference directories merged</span></span>

1.  <span data-ttu-id="88aaf-131">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-131">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="88aaf-132">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="88aaf-132">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="88aaf-133">Compruebe que todos los directorios de conferencia del servidor o grupo de servidores que está combinando estén ahora en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aaf-133">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

