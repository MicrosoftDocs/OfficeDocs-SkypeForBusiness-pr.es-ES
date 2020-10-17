---
title: 'Lync Server 2013: ver detalles acerca de un servicio'
description: 'Lync Server 2013: ver detalles sobre un servicio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09cc5a86748f18a9a032fbf7e90682f46b324902
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572446"
---
# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="4131d-103">Ver los detalles de un servicio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4131d-103">View details about a service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4131d-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4131d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4131d-105">Puede usar el panel de control de Lync Server para ver los detalles de cada servicio que se está ejecutando en un equipo específico de la topología.</span><span class="sxs-lookup"><span data-stu-id="4131d-105">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="4131d-106">Puede ver el estado de cada servicio y los detalles, como por ejemplo, las bases de datos asociadas, puertos y servicios dependientes.</span><span class="sxs-lookup"><span data-stu-id="4131d-106">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="4131d-107">Para ver los detalles de un servicio</span><span class="sxs-lookup"><span data-stu-id="4131d-107">To view details for a service</span></span>

1.  <span data-ttu-id="4131d-108">Desde una cuenta de usuario asignada a cualquiera de los roles administrativos predefinidos para Lync Server 2013, inicie sesión en cualquier equipo de la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4131d-108">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="4131d-109">Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, vea [planeación del control de acceso basado en roles en Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="4131d-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="4131d-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4131d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4131d-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4131d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4131d-112">En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="4131d-112">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="4131d-113">En la página **Estado**, clasifique o busque en la lista y, a continuación, haga clic en el equipo que desee ver.</span><span class="sxs-lookup"><span data-stu-id="4131d-113">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="4131d-114">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4131d-114">Click **Properties**.</span></span>

6.  <span data-ttu-id="4131d-115">En la ventana **Ver detalles de equipo**, clasifique la lista de servicios, si fuera necesario, y haga clic en el servicio de desee ver.</span><span class="sxs-lookup"><span data-stu-id="4131d-115">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="4131d-116">Siga uno de estos procedimientos, según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="4131d-116">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="4131d-117">Para ver el último estado de este servicio en particular, haga clic en **Obtener estado del servicio**.</span><span class="sxs-lookup"><span data-stu-id="4131d-117">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="4131d-118">Para ver los detalles de este servicio en particular, haga clic en **Propiedades** y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4131d-118">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="4131d-119">Para volver a la lista de todos los equipos en la topología, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4131d-119">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4131d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4131d-120">See Also</span></span>


[<span data-ttu-id="4131d-121">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4131d-121">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

