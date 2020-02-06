---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que consistirá en dos o más directores en un grupo de carga equilibrada o en un solo grupo de equipos. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. Para un grupo de equipos de directores, esta es la entrada sistema de nombres de dominio (DNS) de la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga DNS.
ms.openlocfilehash: 491d50c733314e1811aac38c556a6d4683b6956b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796579"
---
# <a name="add-director-pool"></a><span data-ttu-id="631c5-105">Agregar grupo de servidores director</span><span class="sxs-lookup"><span data-stu-id="631c5-105">Add Director Pool</span></span>
 
<span data-ttu-id="631c5-106">Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que consistirá en dos o más directores en un grupo de carga equilibrada o en un **solo grupo de equipos**.</span><span class="sxs-lookup"><span data-stu-id="631c5-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="631c5-107">También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director.</span><span class="sxs-lookup"><span data-stu-id="631c5-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="631c5-108">Para un grupo de equipos de directores, esta es la entrada sistema de nombres de dominio (DNS) de la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="631c5-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="631c5-109">Si piensa implementar un grupo de directores en el futuro, seleccione **varios grupos de equipos**.</span><span class="sxs-lookup"><span data-stu-id="631c5-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="631c5-110">Aunque un grupo se define como dos o más equipos con equilibrio de carga, puede crear un único grupo de equipos y crear un FQDN de grupo para el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="631c5-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="631c5-111">Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología de nuevo para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="631c5-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="631c5-112">También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, el equilibrio de carga del sistema de nombres de dominio (DNS) o los equilibradores de carga del hardware.</span><span class="sxs-lookup"><span data-stu-id="631c5-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="631c5-113">En muchos casos, dispondrá de ambos sistemas de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="631c5-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="631c5-114">Asegúrese de agregar el nuevo servidor miembro a ambos.</span><span class="sxs-lookup"><span data-stu-id="631c5-114">Be sure that you are adding the new member server to both.</span></span> 
  

