---
title: Agregar grupo de servidores director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir el FQDN del grupo de directores, seleccione un grupo de varios equipos que constará de dos o más directores en un grupo de carga equilibrada o en un grupo de servidores de un solo equipo. También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director. En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219491"
---
# <a name="add-director-pool"></a><span data-ttu-id="53d66-105">Agregar grupo de servidores director</span><span class="sxs-lookup"><span data-stu-id="53d66-105">Add Director Pool</span></span>
 
<span data-ttu-id="53d66-106">Para **definir el FQDN del grupo de directores**, seleccione un **grupo de varios equipos** que constará de dos o más directores en un grupo de carga equilibrada o en un grupo de servidores de un **solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="53d66-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="53d66-107">También debe escribir el nombre de dominio completo (FQDN) que se usará para conectarse al grupo de directores o el FQDN de un solo Director.</span><span class="sxs-lookup"><span data-stu-id="53d66-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="53d66-108">En el caso de un grupo de servidores de equipos directores, sería la entrada del Sistema de nombres de dominio (DNS) para la IP virtual de un equilibrador de carga de hardware o la entrada DNS compartida para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="53d66-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="53d66-109">Si tiene previsto implementar un grupo de servidores director, seleccione **Grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="53d66-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="53d66-110">Aunque un grupo se define como dos o más equipos con equilibrio de carga, puede crear un grupo de un solo equipo y crear un FQDN de grupo de servidores para el único equipo.</span><span class="sxs-lookup"><span data-stu-id="53d66-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="53d66-111">Cuando esté preparado para agregar más equipos al grupo más adelante, debe volver a ejecutar el generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de directores mediante el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="53d66-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="53d66-112">También debe agregar el nuevo miembro del grupo de servidores a los equilibradores de carga apropiados para el grupo de servidores, para el equilibrio de carga del sistema de nombres de dominio (DNS) o para equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="53d66-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="53d66-113">En muchos casos, tendrá ambos sistemas de equilibrio de carga en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="53d66-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="53d66-114">Compruebe que el nuevo servidor miembro se agregue a ambos.</span><span class="sxs-lookup"><span data-stu-id="53d66-114">Be sure that you are adding the new member server to both.</span></span> 
  

