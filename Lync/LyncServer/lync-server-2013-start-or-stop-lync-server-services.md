---
title: 'Lync Server 2013: iniciar o detener los servicios de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4396a6110337cfb9d3abdbd8136c78246b12bced
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="667a3-102">Inicio o detención de los servicios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="667a3-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="667a3-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="667a3-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="667a3-104">Puede usar el panel de control de Lync Server para iniciar o detener todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.</span><span class="sxs-lookup"><span data-stu-id="667a3-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="667a3-105">Para iniciar o detener todos los servicios de Lync Server en un equipo:</span><span class="sxs-lookup"><span data-stu-id="667a3-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="667a3-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="667a3-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="667a3-107">Puede determinar si se le ha asignado la CsServerAdministrator o el rol RBAC de CsAdministrator ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="667a3-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="667a3-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="667a3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="667a3-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="667a3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="667a3-110">En la barra de navegación izquierda, haga clic en **Topología** y después en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="667a3-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="667a3-111">En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta los servicios que desea iniciar o detener, y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="667a3-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="667a3-112">Haga clic en **Acción**.</span><span class="sxs-lookup"><span data-stu-id="667a3-112">Click **Action**.</span></span>

6.  <span data-ttu-id="667a3-113">Haga clic en **Iniciar todos los servicios** o **Detener todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="667a3-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="667a3-114">Para iniciar o detener un servicio específico:</span><span class="sxs-lookup"><span data-stu-id="667a3-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="667a3-115">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="667a3-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="667a3-116">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="667a3-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="667a3-117">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="667a3-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="667a3-118">En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="667a3-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="667a3-119">En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="667a3-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="667a3-120">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="667a3-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="667a3-121">Ordene la lista de servicios si es necesario y haga clic en el servicio que desea iniciar o detener.</span><span class="sxs-lookup"><span data-stu-id="667a3-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="667a3-122">Haga clic en **Acción**.</span><span class="sxs-lookup"><span data-stu-id="667a3-122">Click **Action**.</span></span>

8.  <span data-ttu-id="667a3-123">Haga clic en **Iniciar servicio** o **Detener servicio**.</span><span class="sxs-lookup"><span data-stu-id="667a3-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="667a3-124">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="667a3-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="667a3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="667a3-125">See Also</span></span>


[<span data-ttu-id="667a3-126">Impedir sesiones para servicios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="667a3-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="667a3-127">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="667a3-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

