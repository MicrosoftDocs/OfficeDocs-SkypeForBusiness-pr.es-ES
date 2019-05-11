---
title: Agregar grupo de servidores MCU de A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Todos los servidores Enterprise Edition Front-End de un sitio central que no tienen un combinados A / servicio de conferencia A/v puede usar el mismo A independiente o grupo de servidores de conferencia A/v. Para cada A / grupo de servidores de conferencia A/v, debe especificar un nombre de dominio completo (FQDN) para el grupo de servidores y si va a tener solo un único / servidor de conferencia A/v o múltiple, con equilibrio de carga A / servidores de conferencia A/v.
ms.openlocfilehash: dd2dd53ae2d3b66da88d39567b4d20e0960633e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889324"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="ee7aa-104">Agregar grupo de servidores MCU de A/V</span><span class="sxs-lookup"><span data-stu-id="ee7aa-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="ee7aa-105">Todos los servidores Enterprise Edition Front-End de un sitio central que no tienen un combinados A / servicio de conferencia A/v puede usar el mismo A independiente o grupo de servidores de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="ee7aa-106">Para cada A / grupo de servidores de conferencia A/v, debe especificar un nombre de dominio completo (FQDN) para el grupo de servidores y si va a tener solo un único / servidor de conferencia A/v o múltiple, con equilibrio de carga A / servidores de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ee7aa-107">No se puede convertir un grupo de servidores de un único servidor a un grupo de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="ee7aa-108">Si más adelante decide que la organización necesita un grupo de servidores de varios servidores, debe eliminar el grupo de servidores de un solo servidor y, a continuación, agregue el grupo de servidores de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ee7aa-109">Si tiene previsto implementar un grupo de servidores de conferencia A/v en el futuro, seleccione **el grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="ee7aa-110">Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="ee7aa-111">Cuando esté listo para agregar más equipos al grupo de servidores más adelante, debe generador de nuevo para definir el nuevo integrante de grupo de servidores, publique la nueva topología y, a continuación, configurar el nuevo grupo de conferencia A/v miembro a través de la Skype para el Asistente para la implementación de servidor de Business.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="ee7aa-112">A los grupos de servidores de servidor de conferencia A/v son únicos en que no necesitan equilibradores de carga para crear un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="ee7aa-113">A los grupos de servidores de conferencia A/v equilibrar la carga internamente y no es necesario hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

