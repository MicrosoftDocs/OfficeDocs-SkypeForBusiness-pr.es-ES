---
title: Agregar FQDN del grupo de servidores front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique el nombre de dominio completo (FQDN) del grupo de servidores front-end que está creando. No puede cambiar el FQDN de un grupo después de publicar la topología que contiene el grupo de servidores front-end. Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo y, a continuación, agregar un nuevo grupo con el nuevo FQDN.
ms.openlocfilehash: 0d05455a1b57394eaf0b6b11c70d3a6e9d1f84ae
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689329"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="2b4a6-105">Agregar FQDN del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="2b4a6-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="2b4a6-106">Especifique el nombre de dominio completo (FQDN) del grupo de servidores front-end que está creando.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="2b4a6-107">No puede cambiar el FQDN de un grupo después de publicar la topología que contiene el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="2b4a6-108">Si necesita cambiar el nombre de un grupo de servidores, debe eliminar el grupo y, a continuación, agregar un nuevo grupo con el nuevo FQDN.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="2b4a6-109">Si piensa implementar un grupo front-end en el futuro, seleccione **varios grupos de equipos**.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="2b4a6-110">Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="2b4a6-111">Cuando esté listo para agregar más equipos al grupo más adelante, debe ejecutar el generador de topología de nuevo para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores front-end con el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="2b4a6-112">También debe agregar el nuevo miembro del grupo a los equilibradores de carga adecuados para el grupo, el equilibrio de carga del sistema de nombres de dominio (DNS) o los equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="2b4a6-113">En muchos casos, tendríamos ambos sistemas de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="2b4a6-114">Asegúrese de agregar el nuevo servidor miembro a ambos.</span><span class="sxs-lookup"><span data-stu-id="2b4a6-114">Be sure that you are adding the new member server to both.</span></span> 
  

