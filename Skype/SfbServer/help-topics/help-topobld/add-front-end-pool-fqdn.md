---
title: Agregar FQDN del grupo de servidores front-end
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
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique el nombre de dominio completo del grupo de servidores front-end que está creando. El nombre de dominio completo de un grupo de servidores no puede cambiarse una vez publicada la topología que contiene el grupo de servidores front-end. Para cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y agregar un nuevo grupo con el nuevo nombre de dominio completo.
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218861"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="f6ed1-105">Agregar FQDN del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f6ed1-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="f6ed1-p102">Especifique el nombre de dominio completo del grupo de servidores front-end que está creando. El nombre de dominio completo de un grupo de servidores no puede cambiarse una vez publicada la topología que contiene el grupo de servidores front-end. Para cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y agregar un nuevo grupo con el nuevo nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="f6ed1-109">Si tiene previsto implementar un grupo de servidores front-end, seleccione **Grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f6ed1-110">Aunque se defina un grupo de servidores como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f6ed1-111">Cuando esté preparado para agregar más equipos al grupo más adelante, debe volver a ejecutar el generador de topologías para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores front-end mediante el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f6ed1-112">Asimismo, debe agregar el nuevo miembro del grupo de servidores al correspondiente equilibrador de carga, equilibrio de carga del Sistema de nombres de dominio (DNS) o equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="f6ed1-113">En muchos casos, tendrá los dos sistemas de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="f6ed1-114">Compruebe que el nuevo servidor miembro se agregue a ambos.</span><span class="sxs-lookup"><span data-stu-id="f6ed1-114">Be sure that you are adding the new member server to both.</span></span> 
  

