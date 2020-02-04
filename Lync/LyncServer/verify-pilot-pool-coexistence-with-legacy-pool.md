---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="0ebf5-102">Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado</span><span class="sxs-lookup"><span data-stu-id="0ebf5-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ebf5-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0ebf5-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0ebf5-104">Después de implementar el grupo piloto, debe comprobar la coexistencia de las dos agrupaciones mediante las herramientas administrativas para ver la información del grupo.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="0ebf5-105">Para los grupos de 2013 y los grupos heredados de Lync Server, debe usar las herramientas del panel de control y del generador de topologías de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="0ebf5-106">Comprobar que los servicios de Lync Server 2013 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="0ebf5-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="0ebf5-107">En el servidor front-end de Lync Server 2013, vaya al subprograma Servicios de herramientas\\administrativas.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="0ebf5-108">Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="0ebf5-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="0ebf5-109">**Servicios de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="0ebf5-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="0ebf5-110">![Lista de servicios de Lync Server iniciada](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Lista de servicios de Lync Server iniciada")</span><span class="sxs-lookup"><span data-stu-id="0ebf5-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="0ebf5-111">Abrir el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ebf5-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="0ebf5-112">Desde el servidor front-end de su implementación de Lync Server 2013, abra el panel de control de Lync Server 2013 y seleccione el grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="0ebf5-113">Repita el procedimiento para abrir el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="0ebf5-114">**Abrir el panel de control de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="0ebf5-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="0ebf5-115">![Cuadro de diálogo Seleccionar dirección URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Cuadro de diálogo Seleccionar dirección URL")</span><span class="sxs-lookup"><span data-stu-id="0ebf5-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0ebf5-116">En Lync Server 2013, debe actualizar Silverlight a la versión 5 antes de usar el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="0ebf5-117">Esta topología incluye ahora los roles de servidor de Lync Server 2010 y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="0ebf5-118">**Página de topología del panel de control 2013 de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="0ebf5-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="0ebf5-119">![Panel de control de Lync Server-página de topología](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Panel de control de Lync Server-página de topología")</span><span class="sxs-lookup"><span data-stu-id="0ebf5-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="0ebf5-120">No intente abrir la topología en el generador de topología de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0ebf5-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="0ebf5-121">Si intenta abrir la topología con el generador de topología de Lync Server 2010, encontrará el error siguiente.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="0ebf5-122">La topología solo se puede ver con el generador de topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="0ebf5-123">El generador de topología de Lync Server 2013 debe usarse para crear grupos para Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ebf5-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="0ebf5-124">**Mensaje de error del generador de topología 2010 de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="0ebf5-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="0ebf5-125">![Error de acoplamiento de MMC del generador de topología de Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Error de acoplamiento de MMC del generador de topología de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="0ebf5-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

