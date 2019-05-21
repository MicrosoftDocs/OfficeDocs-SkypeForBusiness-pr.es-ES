---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar el grupo piloto, debe actualizar las entradas del host DNS A para la agrupación piloto. Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289626"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="8a70a-104">Configurar registros DNS para una implementación de grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="8a70a-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="8a70a-105">Antes de implementar el grupo piloto, debe actualizar las entradas del host DNS A para la agrupación piloto.</span><span class="sxs-lookup"><span data-stu-id="8a70a-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="8a70a-106">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="8a70a-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="8a70a-107">Para configurar registros A de host DNS</span><span class="sxs-lookup"><span data-stu-id="8a70a-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="8a70a-108">En el servidor del sistema de nombres de dominio (DNS), haga clic en **Inicio**, en **herramientas administrativas**y, por último, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8a70a-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="8a70a-109">En el árbol de consola de su dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón derecho en el dominio en el que se instalará Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8a70a-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="8a70a-110">Haga clic en **nuevo host (A o aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="8a70a-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="8a70a-111">Haga clic en **nombre**, escriba el nombre de host para el grupo de servidores de Skype empresarial 2019 (el nombre de dominio se supone de la zona en la que está definido el registro y no tiene que especificarse como parte del registro A).</span><span class="sxs-lookup"><span data-stu-id="8a70a-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="8a70a-112">Haga clic en **dirección IP**y, a continuación, escriba la dirección IP del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8a70a-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="8a70a-113">Haga clic en **Agregar host**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a70a-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="8a70a-114">Cuando haya terminado, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="8a70a-114">When you are finished, click **Done**.</span></span>
    

