---
title: 'Lync Server 2013: iniciar o detener servicios de Lync Server'
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
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="3ea94-102">Iniciar o detener servicios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea94-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea94-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="3ea94-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="3ea94-104">Puede usar el panel de control de Lync Server para iniciar o detener todos los servicios de Lync Server 2013 que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.</span><span class="sxs-lookup"><span data-stu-id="3ea94-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="3ea94-105">Para iniciar o detener todos los servicios de Lync Server en un equipo</span><span class="sxs-lookup"><span data-stu-id="3ea94-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="3ea94-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ea94-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="3ea94-107">Puede determinar si se le ha asignado el rol de CsServerAdministrator o el rol de RBAC de CsAdministrator ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ea94-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="3ea94-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea94-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3ea94-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ea94-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3ea94-110">En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="3ea94-111">En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios que desea iniciar o detener y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="3ea94-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="3ea94-112">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-112">Click **Action**.</span></span>

6.  <span data-ttu-id="3ea94-113">Haga clic en **iniciar todos los servicios** o en **detener todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="3ea94-114">Para iniciar o detener un servicio específico</span><span class="sxs-lookup"><span data-stu-id="3ea94-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="3ea94-115">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3ea94-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ea94-116">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea94-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3ea94-117">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ea94-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3ea94-118">En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="3ea94-119">En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="3ea94-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="3ea94-120">Haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="3ea94-121">Ordene la lista de servicios, si es necesario, y haga clic en el servicio que desea iniciar o detener.</span><span class="sxs-lookup"><span data-stu-id="3ea94-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="3ea94-122">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-122">Click **Action**.</span></span>

8.  <span data-ttu-id="3ea94-123">Haga clic en **Iniciar servicio** o **Detener servicio**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="3ea94-124">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="3ea94-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ea94-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ea94-125">See Also</span></span>


[<span data-ttu-id="3ea94-126">Evitar las sesiones de servicios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea94-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="3ea94-127">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea94-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

