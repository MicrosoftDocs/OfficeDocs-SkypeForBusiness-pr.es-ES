---
title: Impedir sesiones para servicios
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede usar el panel de control de instalaciones heredadas para evitar nuevas sesiones para todos los servicios heredados que se ejecutan en un equipo específico o para impedir que se realicen nuevas sesiones para un servicio heredado específico.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752292"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="75c72-103">Impedir sesiones para servicios</span><span class="sxs-lookup"><span data-stu-id="75c72-103">Prevent sessions for services</span></span>

<span data-ttu-id="75c72-104">Puede usar el panel de control de instalaciones heredadas para evitar nuevas sesiones para todos los servicios heredados que se ejecutan en un equipo específico o para impedir que se realicen nuevas sesiones para un servicio heredado específico.</span><span class="sxs-lookup"><span data-stu-id="75c72-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="75c72-105">Para evitar nuevas sesiones para servicios en un equipo</span><span class="sxs-lookup"><span data-stu-id="75c72-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="75c72-106">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que implementó Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="75c72-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="75c72-107">Abra el panel de control de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="75c72-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="75c72-108">En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="75c72-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="75c72-109">En la página \*\*Estado \*\*, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="75c72-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="75c72-110">Haga clic en **Acción**.</span><span class="sxs-lookup"><span data-stu-id="75c72-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="75c72-111">Haga clic en \*\*Evitar sesiones nuevas en todos los servicios \*\*.</span><span class="sxs-lookup"><span data-stu-id="75c72-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="75c72-112">Para impedir que se creen sesiones nuevas para un servicio específico</span><span class="sxs-lookup"><span data-stu-id="75c72-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="75c72-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que implementó Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="75c72-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="75c72-114">Abra el panel de control de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="75c72-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="75c72-115">En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="75c72-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="75c72-116">En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="75c72-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="75c72-117">Haga clic en \*\*Propiedades \*\*.</span><span class="sxs-lookup"><span data-stu-id="75c72-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="75c72-118">Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="75c72-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="75c72-119">Haga clic en \*\*Acción \*\*.</span><span class="sxs-lookup"><span data-stu-id="75c72-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="75c72-120">Haga clic en \*\*Evitar sesiones nuevas en el servicio \*\*.</span><span class="sxs-lookup"><span data-stu-id="75c72-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="75c72-121">Haga clic en \*\*Cerrar \*\*.</span><span class="sxs-lookup"><span data-stu-id="75c72-121">Click **Close**.</span></span>
    

