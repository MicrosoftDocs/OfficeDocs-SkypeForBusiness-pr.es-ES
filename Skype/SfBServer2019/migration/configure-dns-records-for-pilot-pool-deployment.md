---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
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
description: Antes de implementar el grupo piloto, debe actualizar las entradas del host DNS A para la agrupación piloto. Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813858"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="51007-104">Configurar registros DNS para una implementación de grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="51007-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="51007-105">Antes de implementar el grupo piloto, debe actualizar las entradas del host DNS A para la agrupación piloto.</span><span class="sxs-lookup"><span data-stu-id="51007-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="51007-106">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="51007-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="51007-107">Para configurar registros A de host DNS</span><span class="sxs-lookup"><span data-stu-id="51007-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="51007-108">En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, en **herramientas administrativas**y, por último, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="51007-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="51007-109">En el árbol de consola de su dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón derecho en el dominio en el que se instalará Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="51007-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="51007-110">Haga clic en **nuevo host (A o aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="51007-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="51007-111">Haga clic en **nombre**, escriba el nombre de host para el grupo de servidores de Skype empresarial 2019 (el nombre de dominio se supone de la zona en la que está definido el registro y no tiene que especificarse como parte del registro A).</span><span class="sxs-lookup"><span data-stu-id="51007-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="51007-112">Haga clic en **dirección IP**y, a continuación, escriba la dirección IP del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="51007-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="51007-113">Haga clic en **Agregar host**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="51007-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="51007-114">Cuando haya terminado, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="51007-114">When you are finished, click **Done**.</span></span>
    

