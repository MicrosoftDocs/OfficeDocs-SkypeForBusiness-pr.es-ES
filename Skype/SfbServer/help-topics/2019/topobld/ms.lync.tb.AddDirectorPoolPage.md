---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que se componen de dos o más directores en un grupo de servidores con equilibrio de carga, o un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al FQDN del Director único o el grupo de servidores de Director. Para un grupo de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: f659b45fd758d07b9cf96b59b57654bb8cf2fd28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202211"
---
# <a name="add-director-pool"></a><span data-ttu-id="e1a76-105">Agregar grupo de servidores director</span><span class="sxs-lookup"><span data-stu-id="e1a76-105">Add Director Pool</span></span>
 
<span data-ttu-id="e1a76-106">Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que se componen de dos o más directores en un grupo de servidores con equilibrio de carga, o bien un **grupo de servidores de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="e1a76-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="e1a76-107">También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al FQDN del Director único o el grupo de servidores de Director.</span><span class="sxs-lookup"><span data-stu-id="e1a76-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="e1a76-108">Para un grupo de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="e1a76-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="e1a76-109">Si tiene previsto implementar un grupo de directores en el futuro, seleccione **el grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="e1a76-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="e1a76-110">Aunque un grupo de servidores se define como dos o más equipos que están con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y cree un FQDN del grupo de servidores para el equipo único.</span><span class="sxs-lookup"><span data-stu-id="e1a76-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="e1a76-111">Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe ejecutar el generador de topología de nuevo para definir al nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar al nuevo integrante de grupo de servidores de Director a través de la Skype para Asistente para implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="e1a76-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="e1a76-112">También debe agregar al nuevo integrante de grupo de servidores a los equilibradores de carga adecuada para el grupo de servidores, sistema de nombres de dominio (DNS) equilibrio de carga, o los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="e1a76-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="e1a76-113">En muchos casos, tendrá los sistemas en lugar de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="e1a76-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="e1a76-114">Asegúrese de que haya que agregar el nuevo servidor miembro a ambos.</span><span class="sxs-lookup"><span data-stu-id="e1a76-114">Be sure that you are adding the new member server to both.</span></span> 
  

