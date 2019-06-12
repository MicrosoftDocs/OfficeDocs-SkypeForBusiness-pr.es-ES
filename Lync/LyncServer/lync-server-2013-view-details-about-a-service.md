---
title: 'Lync Server 2013: ver detalles sobre un servicio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fd84ad7290f3b82130f04d8b81955f6ffb4921
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="c8f37-102">Ver los detalles de un servicio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8f37-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8f37-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c8f37-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c8f37-104">Puede usar el panel de control de Lync Server para ver los detalles de cada servicio que se está ejecutando en un equipo específico de su topología.</span><span class="sxs-lookup"><span data-stu-id="c8f37-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="c8f37-105">Puede ver el estado de cada servicio y los detalles como las bases de datos, los puertos y los servicios dependientes asociados.</span><span class="sxs-lookup"><span data-stu-id="c8f37-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="c8f37-106">Para ver los detalles de un servicio</span><span class="sxs-lookup"><span data-stu-id="c8f37-106">To view details for a service</span></span>

1.  <span data-ttu-id="c8f37-107">Desde una cuenta de usuario asignada a cualquiera de los roles administrativos predefinidos para Lync Server 2013, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c8f37-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="c8f37-108">Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, consulte [planificación de control de acceso basado en roles en Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="c8f37-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="c8f37-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8f37-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8f37-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c8f37-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8f37-111">En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="c8f37-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="c8f37-112">En la página **Estado** , ordene o busque en la lista y, a continuación, haga clic en el equipo que desea ver.</span><span class="sxs-lookup"><span data-stu-id="c8f37-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="c8f37-113">Haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c8f37-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="c8f37-114">En la ventana **Ver detalles del equipo** , ordene la lista de servicios, si es necesario, y haga clic en el servicio que desea ver.</span><span class="sxs-lookup"><span data-stu-id="c8f37-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="c8f37-115">Realice una de las siguientes acciones según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="c8f37-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="c8f37-116">Para ver el estado más reciente de ese servicio específico, haga clic en **obtener estado del servicio**.</span><span class="sxs-lookup"><span data-stu-id="c8f37-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="c8f37-117">Para ver los detalles de ese servicio específico, haga clic en **propiedades** y, a continuación, en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c8f37-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="c8f37-118">Para volver a la lista de todos los equipos de su topología, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c8f37-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8f37-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f37-119">See Also</span></span>


[<span data-ttu-id="c8f37-120">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8f37-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

