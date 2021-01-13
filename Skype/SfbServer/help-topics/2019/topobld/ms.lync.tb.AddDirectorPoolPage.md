---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que conste de dos o más directores en un grupo de servidores con equilibrio de carga o un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o al FQDN del director único. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807760"
---
# <a name="add-director-pool"></a><span data-ttu-id="00b8f-105">Agregar grupo de servidores director</span><span class="sxs-lookup"><span data-stu-id="00b8f-105">Add Director Pool</span></span>
 
<span data-ttu-id="00b8f-106">Para **definir el FQDN** del  grupo de directores, seleccione un grupo de servidores de varios equipos que conste de dos o más directores en un grupo de servidores con equilibrio de carga o un grupo de servidores de un **solo equipo.**</span><span class="sxs-lookup"><span data-stu-id="00b8f-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="00b8f-107">También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o al FQDN del director único.</span><span class="sxs-lookup"><span data-stu-id="00b8f-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="00b8f-108">En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="00b8f-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="00b8f-109">Si tiene previsto implementar un grupo de servidores director, seleccione **Grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="00b8f-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="00b8f-110">Aunque un grupo de servidores se define como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y crear un FQDN de grupo para el único equipo.</span><span class="sxs-lookup"><span data-stu-id="00b8f-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="00b8f-111">Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a ejecutar el Generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores a través del Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="00b8f-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="00b8f-112">También debe agregar el nuevo miembro del grupo de servidores a los equilibradores de carga adecuados para el grupo de servidores, para el equilibrio de carga del Sistema de nombres de dominio (DNS) o para equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="00b8f-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="00b8f-113">En muchos casos, tendrá ambos sistemas de equilibrio de carga en su lugar.</span><span class="sxs-lookup"><span data-stu-id="00b8f-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="00b8f-114">Compruebe que el nuevo servidor miembro se agregue a ambos.</span><span class="sxs-lookup"><span data-stu-id="00b8f-114">Be sure that you are adding the new member server to both.</span></span> 
  

