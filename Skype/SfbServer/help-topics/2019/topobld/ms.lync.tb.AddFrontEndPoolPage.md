---
title: Agregar el FQDN del grupo de servidores de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que va a crear. No se puede cambiar el FQDN de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y, a continuación, agregar un nuevo grupo con el FQDN nuevo.
ms.openlocfilehash: 9730c1857ccb68e5aeb05a66d89e306aa9646246
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21068236"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="2fc28-105">Agregar el FQDN del grupo de servidores de Front-End</span><span class="sxs-lookup"><span data-stu-id="2fc28-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="2fc28-106">Especifique el nombre de dominio completo (FQDN) del grupo de servidores Front-End que va a crear.</span><span class="sxs-lookup"><span data-stu-id="2fc28-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="2fc28-107">No se puede cambiar el FQDN de un grupo de servidores después de publicar la topología que contiene el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="2fc28-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="2fc28-108">Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo de servidores y, a continuación, agregar un nuevo grupo con el FQDN nuevo.</span><span class="sxs-lookup"><span data-stu-id="2fc28-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="2fc28-109">Si tiene previsto implementar un grupo de servidores Front-End en el futuro, seleccione **el grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="2fc28-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="2fc28-110">Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="2fc28-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="2fc28-111">Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe ejecutar el generador de topología de nuevo para definir al nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar el nuevo integrante de grupo de servidores Front-End a través de la Skype para el Asistente para la implementación de servidor de negocio.</span><span class="sxs-lookup"><span data-stu-id="2fc28-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="2fc28-112">También debe agregar al nuevo integrante de grupo de servidores a los equilibradores de carga adecuada para el grupo de servidores, el equilibrio de carga del sistema de nombres de dominio (DNS) o equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="2fc28-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="2fc28-113">En muchos casos, tendría los sistemas en lugar de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="2fc28-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="2fc28-114">Asegúrese de que haya que agregar el nuevo servidor miembro a ambos.</span><span class="sxs-lookup"><span data-stu-id="2fc28-114">Be sure that you are adding the new member server to both.</span></span> 
  

