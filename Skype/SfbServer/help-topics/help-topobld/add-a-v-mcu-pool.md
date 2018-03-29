---
title: Añadir A / V MCU Pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos los servidores Enterprise Edition Front End de un sitio central que no tienen un colocadas A / servicio de conferencias audiovisuales puede utilizar la misma independiente / grupo de conferencias audiovisuales. Para cada A / grupo de conferencias audiovisuales, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tiene sólo un único / V Conferencing Server o múltiple, equilibrio de carga A / V servidores de conferencia.
ms.openlocfilehash: d1712829030836446c06a2e335c424d51a19e466
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="17786-104">Añadir A / V MCU Pool</span><span class="sxs-lookup"><span data-stu-id="17786-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="17786-105">Todos los servidores Enterprise Edition Front End de un sitio central que no tienen un colocadas A / servicio de conferencias audiovisuales puede utilizar la misma independiente / grupo de conferencias audiovisuales.</span><span class="sxs-lookup"><span data-stu-id="17786-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="17786-106">Para cada A / grupo de conferencias audiovisuales, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tiene sólo un único / V Conferencing Server o múltiple, equilibrio de carga A / V servidores de conferencia.</span><span class="sxs-lookup"><span data-stu-id="17786-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="17786-107">No se puede convertir un grupo de servidor único a una agrupación de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="17786-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="17786-108">Si más adelante decide que su organización tiene un grupo de varios servidores, debe eliminar el grupo de servidor único y, a continuación, agregue la agrupación de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="17786-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="17786-109">Si piensa implementar una A / grupo de conferencias audiovisuales en el futuro, seleccione **varios grupo de equipo**.</span><span class="sxs-lookup"><span data-stu-id="17786-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="17786-110">Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="17786-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="17786-111">Cuando esté listo para agregar más equipos al grupo posteriormente, primero debe el generador de topología para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo A / conferencias audiovisuales grupo miembro mediante el Skype para el Asistente para implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="17786-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="17786-112">A / grupos V Conferencing Server son exclusivas en tanto no necesita equilibradores de carga para crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="17786-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="17786-113">A / grupos de conferencias audiovisuales equilibrar la carga internamente y no es necesario hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="17786-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

