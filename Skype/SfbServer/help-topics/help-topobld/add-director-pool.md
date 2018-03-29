---
title: Agregar grupo de directores
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de Director, seleccione un grupo de equipo múltiple que constará de dos o más directores en un grupo de servidores con equilibrio de carga, o un grupo de equipo único. También debe escribir el nombre de dominio completo (FQDN) que se utilizará para conectar con el grupo de directores o FQDN del Director único. En el conjunto de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para equilibrar la carga DNS.
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-pool"></a><span data-ttu-id="1ea62-105">Agregar grupo de directores</span><span class="sxs-lookup"><span data-stu-id="1ea62-105">Add Director Pool</span></span>
 
<span data-ttu-id="1ea62-106">Para **definir el FQDN del grupo de Director**, seleccione un **grupo de equipo múltiple** que constará de dos o más directores en un grupo de servidores con equilibrio de carga, o un **grupo de equipo único**.</span><span class="sxs-lookup"><span data-stu-id="1ea62-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="1ea62-107">También debe escribir el nombre de dominio completo (FQDN) que se utilizará para conectar con el grupo de directores o FQDN del Director único.</span><span class="sxs-lookup"><span data-stu-id="1ea62-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="1ea62-108">En el conjunto de equipos de Director, sería la entrada del sistema de nombres de dominio (DNS) para la dirección IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para equilibrar la carga DNS.</span><span class="sxs-lookup"><span data-stu-id="1ea62-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="1ea62-109">Si va a implementar un grupo de directores en el futuro, seleccione **grupo de equipo múltiple**.</span><span class="sxs-lookup"><span data-stu-id="1ea62-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="1ea62-110">Aunque un grupo se define como dos o más equipos que son el equilibrio de carga, puede crear un grupo de equipo único y crear un FQDN del grupo para el equipo único.</span><span class="sxs-lookup"><span data-stu-id="1ea62-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="1ea62-111">Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología para definir al nuevo miembro del grupo, publicar la nueva topología y, a continuación, configure al nuevo miembro del grupo de Director a través del Skype para el Asistente para implementación de servidor de Business.</span><span class="sxs-lookup"><span data-stu-id="1ea62-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="1ea62-112">También debe agregar al nuevo miembro de grupo a los equilibradores de carga adecuada para el grupo de sistema de nombres de dominio (DNS) equilibrio de carga, o equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1ea62-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="1ea62-113">En muchos casos, tendrá los sistemas en lugar de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="1ea62-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="1ea62-114">Asegúrese de que está agregando el nuevo servidor de miembro a ambos.</span><span class="sxs-lookup"><span data-stu-id="1ea62-114">Be sure that you are adding the new member server to both.</span></span> 
  

