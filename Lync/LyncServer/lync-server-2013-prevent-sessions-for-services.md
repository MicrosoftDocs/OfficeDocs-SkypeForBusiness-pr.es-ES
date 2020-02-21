---
title: 'Lync Server 2013: impedir sesiones para servicios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b1737bddb680f597b8009c59dff9e772a7719df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="7d56e-102">Impedir sesiones para servicios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d56e-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d56e-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7d56e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7d56e-104">Puede usar el panel de control de Lync Server para evitar nuevas sesiones para todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para impedir que se realicen nuevas sesiones para un servicio de Lync Server 2013 específico.</span><span class="sxs-lookup"><span data-stu-id="7d56e-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="7d56e-105">Para impedir que se creen sesiones nuevas en todos los servicios de Lync Server en un equipo</span><span class="sxs-lookup"><span data-stu-id="7d56e-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="7d56e-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d56e-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7d56e-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d56e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d56e-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d56e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d56e-109">En la barra de navegación izquierda, haga clic en **Topología** y después en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="7d56e-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="7d56e-110">En la página \*\*Estado \*\*, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="7d56e-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="7d56e-111">Haga clic en **Acción**.</span><span class="sxs-lookup"><span data-stu-id="7d56e-111">Click **Action**.</span></span>

6.  <span data-ttu-id="7d56e-112">Haga clic en \*\*Evitar sesiones nuevas en todos los servicios \*\*.</span><span class="sxs-lookup"><span data-stu-id="7d56e-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="7d56e-113">Para impedir que se creen sesiones nuevas para un servicio específico</span><span class="sxs-lookup"><span data-stu-id="7d56e-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="7d56e-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d56e-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7d56e-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d56e-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d56e-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d56e-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d56e-117">En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="7d56e-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="7d56e-118">En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="7d56e-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="7d56e-119">Haga clic en \*\*Propiedades \*\*.</span><span class="sxs-lookup"><span data-stu-id="7d56e-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="7d56e-120">Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="7d56e-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="7d56e-121">Haga clic en \*\*Acción \*\*.</span><span class="sxs-lookup"><span data-stu-id="7d56e-121">Click **Action**.</span></span>

8.  <span data-ttu-id="7d56e-122">Haga clic en \*\*Evitar sesiones nuevas en el servicio \*\*.</span><span class="sxs-lookup"><span data-stu-id="7d56e-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="7d56e-123">Haga clic en \*\*Cerrar \*\*.</span><span class="sxs-lookup"><span data-stu-id="7d56e-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d56e-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7d56e-124">See Also</span></span>


[<span data-ttu-id="7d56e-125">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d56e-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

