---
title: Impedir sesiones para servicios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede usar el Panel de Control de las instalaciones heredadas para evitar sesiones nuevas en todos los servicios heredados que se ejecutan en un equipo específico o para evitar sesiones nuevas para un servicio específico de heredado.
ms.openlocfilehash: 9f3f9bb301841d7e71c18f4d3ca052f3d0c74dce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875535"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="1bf17-103">Impedir sesiones para servicios</span><span class="sxs-lookup"><span data-stu-id="1bf17-103">Prevent sessions for services</span></span>

<span data-ttu-id="1bf17-104">Puede usar el Panel de Control de las instalaciones heredadas para evitar sesiones nuevas en todos los servicios heredados que se ejecutan en un equipo específico o para evitar sesiones nuevas para un servicio específico de heredado.</span><span class="sxs-lookup"><span data-stu-id="1bf17-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="1bf17-105">Para evitar que las sesiones nuevas para los servicios en un equipo</span><span class="sxs-lookup"><span data-stu-id="1bf17-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="1bf17-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1bf17-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="1bf17-107">Abra Skype para el Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="1bf17-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="1bf17-108">En la barra de navegación izquierda, haga clic en \*\*Topología \*\* y, a continuación, en \*\*Estado \*\*. </span><span class="sxs-lookup"><span data-stu-id="1bf17-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="1bf17-109">En la página **estado** , ordenación o búsqueda a través de la lista como sea necesario para encontrar el equipo que ejecuta los servicios para la que desea impedir nuevas sesiones y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="1bf17-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="1bf17-110">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="1bf17-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="1bf17-111">Haga clic en **evitar sesiones nuevas en todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="1bf17-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="1bf17-112">Para evitar que las sesiones nuevas para un servicio específico</span><span class="sxs-lookup"><span data-stu-id="1bf17-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="1bf17-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1bf17-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="1bf17-114">Abra Skype para el Panel de Control.</span><span class="sxs-lookup"><span data-stu-id="1bf17-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="1bf17-115">En la barra de navegación izquierda, haga clic en \*\*Topología \*\* y, a continuación, en \*\*Estado \*\*. </span><span class="sxs-lookup"><span data-stu-id="1bf17-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="1bf17-116">En la página de **estado** , la ordenación o la búsqueda a través de la lista según sea necesario para encontrar el equipo que ejecuta el servicio que desea iniciar o detener y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="1bf17-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="1bf17-117">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1bf17-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="1bf17-118">Ordenar la lista de servicios, si es necesario y haga clic en el servicio para la que desea impedir nuevas sesiones.</span><span class="sxs-lookup"><span data-stu-id="1bf17-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="1bf17-119">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="1bf17-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="1bf17-120">Haga clic en **evitar sesiones nuevas para el servicio**.</span><span class="sxs-lookup"><span data-stu-id="1bf17-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="1bf17-121">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1bf17-121">Click **Close**.</span></span>
    

