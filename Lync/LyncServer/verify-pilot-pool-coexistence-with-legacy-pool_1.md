---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="d782a-102">Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado</span><span class="sxs-lookup"><span data-stu-id="d782a-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d782a-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d782a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="d782a-104">Comprobar el grupo en la herramienta administrativa de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d782a-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="d782a-105">Abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d782a-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="d782a-106">Expanda el nodo **bosque** , expanda el nodo **servidores Standard Edition** o grupos de servidores **Enterprise** y, a continuación, expanda el nombre del servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d782a-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="d782a-107">Asegúrese de que los servicios de Office Communications Server 2007 R2 se están ejecutando en el grupo.</span><span class="sxs-lookup"><span data-stu-id="d782a-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="d782a-108">![Consola de administración de Office Communications Server 2007 R2] (images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="d782a-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="d782a-109">Comprobar la agrupación piloto en el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d782a-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="d782a-110">Desde una cuenta de usuario que sea miembro del rol CsAdministrator, inicie sesión en el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d782a-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="d782a-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d782a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d782a-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d782a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d782a-113">Haga clic en **topología**.</span><span class="sxs-lookup"><span data-stu-id="d782a-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="d782a-114">Verifique que los servidores que ha implementado estén presentes en el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="d782a-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="d782a-115">![Página de topología del panel de control de Lync Server] (images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Página de topología del panel de control de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="d782a-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="d782a-116">Comprobar que los servicios de Lync Server 2013 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="d782a-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="d782a-117">En el servidor front-end de Lync Server 2013, abra el subprograma **servicios** desde el grupo **herramientas administrativas** .</span><span class="sxs-lookup"><span data-stu-id="d782a-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="d782a-118">Verifique que los servicios enumerados coincidan con la lista de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="d782a-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="d782a-119">![Página de servicios que muestra los servicios de Lync iniciados] (images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Página de servicios que muestra los servicios de Lync iniciados")</span><span class="sxs-lookup"><span data-stu-id="d782a-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

