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
ms.openlocfilehash: dc90e58fecf5e386600ca91cf764dbb50f9d76c7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="fa4db-102">Evitar las sesiones de servicios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa4db-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa4db-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fa4db-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fa4db-104">Puede usar el panel de control de Lync Server para evitar nuevas sesiones para todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio específico de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa4db-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="fa4db-105">Para evitar nuevas sesiones para todos los servicios de Lync Server en un equipo</span><span class="sxs-lookup"><span data-stu-id="fa4db-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="fa4db-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa4db-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fa4db-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa4db-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fa4db-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fa4db-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fa4db-109">En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="fa4db-110">En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios para los que desea evitar nuevas sesiones y, a continuación, haga clic en ella.</span><span class="sxs-lookup"><span data-stu-id="fa4db-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="fa4db-111">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-111">Click **Action**.</span></span>

6.  <span data-ttu-id="fa4db-112">Haga clic en **evitar nuevas sesiones para todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="fa4db-113">Para evitar nuevas sesiones para un servicio específico</span><span class="sxs-lookup"><span data-stu-id="fa4db-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="fa4db-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa4db-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fa4db-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa4db-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fa4db-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fa4db-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fa4db-117">En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="fa4db-118">En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="fa4db-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="fa4db-119">Haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="fa4db-120">Si es necesario, ordene la lista de servicios y haga clic en el servicio para el que desea evitar nuevas sesiones.</span><span class="sxs-lookup"><span data-stu-id="fa4db-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="fa4db-121">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-121">Click **Action**.</span></span>

8.  <span data-ttu-id="fa4db-122">Haga clic en **evitar nuevas sesiones para el servicio**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="fa4db-123">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="fa4db-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa4db-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa4db-124">See Also</span></span>


[<span data-ttu-id="fa4db-125">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa4db-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

