---
title: Impedir sesiones para servicios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede usar el panel de control instalaciones heredadas para evitar nuevas sesiones para todos los servicios heredados que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio heredado específico.
ms.openlocfilehash: 5bba30bee0fb8c25bed25e2c3cbd593179aa9b97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813058"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="9bc5c-103">Impedir sesiones para servicios</span><span class="sxs-lookup"><span data-stu-id="9bc5c-103">Prevent sessions for services</span></span>

<span data-ttu-id="9bc5c-104">Puede usar el panel de control instalaciones heredadas para evitar nuevas sesiones para todos los servicios heredados que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio heredado específico.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="9bc5c-105">Para evitar nuevas sesiones de servicios en un equipo</span><span class="sxs-lookup"><span data-stu-id="9bc5c-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="9bc5c-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="9bc5c-107">Abre el panel de control de Skype para empresas.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="9bc5c-108">En la barra de navegación izquierda, haga clic en \*\*Topología \*\* y, a continuación, en \*\*Estado \*\*. </span><span class="sxs-lookup"><span data-stu-id="9bc5c-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="9bc5c-109">En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios para los que desea evitar nuevas sesiones y, a continuación, haga clic en ella.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="9bc5c-110">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="9bc5c-111">Haga clic en **evitar nuevas sesiones para todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="9bc5c-112">Para evitar nuevas sesiones para un servicio específico</span><span class="sxs-lookup"><span data-stu-id="9bc5c-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="9bc5c-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="9bc5c-114">Abre el panel de control de Skype para empresas.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="9bc5c-115">En la barra de navegación izquierda, haga clic en \*\*Topología \*\* y, a continuación, en \*\*Estado \*\*. </span><span class="sxs-lookup"><span data-stu-id="9bc5c-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="9bc5c-116">En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="9bc5c-117">Haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="9bc5c-118">Si es necesario, ordene la lista de servicios y haga clic en el servicio para el que desea evitar nuevas sesiones.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="9bc5c-119">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="9bc5c-120">Haga clic en **evitar nuevas sesiones para el servicio**.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="9bc5c-121">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9bc5c-121">Click **Close**.</span></span>
    

