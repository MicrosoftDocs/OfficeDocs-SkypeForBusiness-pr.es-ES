---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar el grupo piloto, debe actualizar las entradas de Host DNS A para el grupo piloto. Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.
ms.openlocfilehash: 23ac5e4f85dc0da560b4d288bbfad426298bf82e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872742"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="1c716-104">Configurar registros DNS para una implementación de grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="1c716-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="1c716-105">Antes de implementar el grupo piloto, debe actualizar las entradas de Host DNS A para el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="1c716-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="1c716-106">Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="1c716-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="1c716-107">Para configurar los registros de Host DNS A</span><span class="sxs-lookup"><span data-stu-id="1c716-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="1c716-108">En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1c716-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="1c716-109">En el árbol de consola del dominio, expanda **Zonas de búsqueda directa**y, a continuación, haga clic en el dominio en el que se va a instalar Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1c716-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="1c716-110">Haga clic en **Host nuevo (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="1c716-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="1c716-111">Haga clic en **nombre**, escriba el nombre de host para el Skype para grupo de negocio Server 2019 (el nombre de dominio se deduce de la zona que se define en el registro y que no es necesario que debe escribirse como parte del registro A).</span><span class="sxs-lookup"><span data-stu-id="1c716-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="1c716-112">Haga clic en **Dirección IP**y, a continuación, escriba la dirección IP para el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="1c716-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="1c716-113">Haga clic en **Agregar Host**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1c716-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="1c716-114">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="1c716-114">When you are finished, click **Done**.</span></span>
    

