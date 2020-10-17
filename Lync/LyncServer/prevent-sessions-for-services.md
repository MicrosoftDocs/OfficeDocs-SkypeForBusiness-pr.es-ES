---
title: Impedir sesiones para servicios
description: Impedir sesiones para los servicios.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563696"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="e6522-103">Impedir sesiones para servicios</span><span class="sxs-lookup"><span data-stu-id="e6522-103">Prevent sessions for services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6522-104">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="e6522-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="e6522-105">Puede usar el panel de control de Microsoft Lync Server 2010 para evitar nuevas sesiones para todos los servicios de Lync Server 2010 que se ejecutan en un equipo específico o para impedir que se realicen nuevas sesiones para un servicio de Lync Server 2010 específico.</span><span class="sxs-lookup"><span data-stu-id="e6522-105">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="e6522-106">Para impedir que se creen sesiones nuevas en todos los servicios de Lync Server en un equipo</span><span class="sxs-lookup"><span data-stu-id="e6522-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="e6522-107">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6522-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e6522-108">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e6522-108">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="e6522-109">En la barra de navegación izquierda, haga clic en \*\*Topología \*\* y, a continuación, en \*\*Estado \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="e6522-110">En la página \*\*Estado \*\*, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="e6522-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="e6522-111">Haga clic en \*\*Acción \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-111">Click **Action**.</span></span>

6.  <span data-ttu-id="e6522-112">Haga clic en \*\*Evitar sesiones nuevas en todos los servicios \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="e6522-113">Para impedir que se creen sesiones nuevas para un servicio específico</span><span class="sxs-lookup"><span data-stu-id="e6522-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="e6522-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6522-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e6522-115">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e6522-115">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="e6522-116">En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="e6522-116">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="e6522-117">En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="e6522-117">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="e6522-118">Haga clic en \*\*Propiedades \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-118">Click **Properties**.</span></span>

6.  <span data-ttu-id="e6522-119">Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="e6522-119">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="e6522-120">Haga clic en \*\*Acción \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-120">Click **Action**.</span></span>

8.  <span data-ttu-id="e6522-121">Haga clic en \*\*Evitar sesiones nuevas en el servicio \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-121">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="e6522-122">Haga clic en \*\*Cerrar \*\*.</span><span class="sxs-lookup"><span data-stu-id="e6522-122">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

