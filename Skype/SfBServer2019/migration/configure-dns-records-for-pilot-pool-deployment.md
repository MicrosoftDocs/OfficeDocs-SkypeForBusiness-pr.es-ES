---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
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
description: Antes de implementar el grupo piloto, debe actualizar las entradas de host DNS A para el grupo piloto. Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754060"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="4d1bc-104">Configurar registros DNS para una implementación de grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="4d1bc-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="4d1bc-105">Antes de implementar el grupo piloto, debe actualizar las entradas de host DNS A para el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="4d1bc-106">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="4d1bc-107">Para configurar los registros de host DNS A</span><span class="sxs-lookup"><span data-stu-id="4d1bc-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="4d1bc-108">En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, \*\*Herramientas administrativas \*\* y, a continuación, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="4d1bc-109">En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="4d1bc-110">Haga clic en **Host nuevo (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="4d1bc-111">Haga clic en **nombre**, escriba el nombre de host del grupo de servidores de Skype empresarial Server 2019 (el nombre de dominio se asume de la zona en la que está definido el registro y no es necesario especificarlo como parte del registro A).</span><span class="sxs-lookup"><span data-stu-id="4d1bc-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="4d1bc-112">Haga clic en **dirección IP**y, a continuación, escriba la dirección IP del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="4d1bc-113">Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="4d1bc-114">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-114">When you are finished, click **Done**.</span></span>
    

