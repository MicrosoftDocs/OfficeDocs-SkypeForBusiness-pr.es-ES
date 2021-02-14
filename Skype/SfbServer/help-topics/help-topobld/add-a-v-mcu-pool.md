---
title: Agregar grupo de servidores MCU de A/V
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos los servidores front-end de Enterprise Edition de un sitio central que no tengan instalado un servicio de conferencias A/V puede usar el mismo grupo independiente de servidores de conferencia A/V. En cada grupo de servidores de conferencia A/V, debe especificar un nombre de dominio completo para el grupo de servidores, además de indicar si habrá un solo servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.
ms.openlocfilehash: 689f91bd27e4b3bbb2bd31149f34438bac59db46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810470"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="293d6-104">Agregar grupo de servidores MCU de A/V</span><span class="sxs-lookup"><span data-stu-id="293d6-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="293d6-p102">Todos los servidores front-end de Enterprise Edition de un sitio central que no tengan instalado un servicio de conferencias A/V puede usar el mismo grupo independiente de servidores de conferencia A/V. En cada grupo de servidores de conferencia A/V, debe especificar un nombre de dominio completo para el grupo de servidores, además de indicar si habrá un solo servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="293d6-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="293d6-p103">Un grupo de servidores de un solo servidor no puede convertirse en un grupo de servidores de varios servidores. Si más adelante considera que la organización necesita un grupo de servidores de varios servidores, debe eliminar el grupo de servidores de un solo servidor y, a continuación, agregar el grupo de servidores de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="293d6-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="293d6-109">Si tiene previsto implementar un grupo de servidores de conferencia A/V, deseleccione **Grupo de servidores de varios equipos**.</span><span class="sxs-lookup"><span data-stu-id="293d6-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="293d6-110">Aunque se defina un grupo de servidores como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="293d6-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="293d6-111">Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a definir el nuevo miembro del grupo de servidores, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de servidores de conferencia A/V a través del Asistente para la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="293d6-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="293d6-112">Los grupos de servidores de conferencia A/V son únicos ya que no necesitan equilibradores de carga para crear un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="293d6-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="293d6-113">Estos grupos equilibran la carga internamente y no necesitan de hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="293d6-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

