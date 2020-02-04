---
title: Agregar grupo de servidores MCU de A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos los servidores de aplicaciones para el usuario de Enterprise Edition de un sitio central que no dispongan de un servicio de conferencia A/V, pueden usar el mismo grupo independiente de conferencias A/V. Para cada grupo de conferencias A/V, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tendrá un único servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.
ms.openlocfilehash: cf34ca6b82f31b0232748d15f0b0cc6597511249
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685393"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="0043c-104">Agregar grupo de servidores MCU de A/V</span><span class="sxs-lookup"><span data-stu-id="0043c-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="0043c-105">Todos los servidores de aplicaciones para el usuario de Enterprise Edition de un sitio central que no dispongan de un servicio de conferencia A/V, pueden usar el mismo grupo independiente de conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="0043c-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="0043c-106">Para cada grupo de conferencias A/V, debe especificar un nombre de dominio completo (FQDN) para el grupo y si tendrá un único servidor de conferencia A/V o varios servidores de conferencia A/V con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="0043c-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0043c-107">No se puede convertir un grupo de un solo servidor en un grupo de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="0043c-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="0043c-108">Si más tarde decide que su organización necesita un grupo de varios servidores, debe eliminar el grupo de servidores únicos y, a continuación, agregar el grupo de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="0043c-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="0043c-109">Si piensa implementar un grupo de conferencias A/V en el futuro, seleccione **varios grupos de equipos**.</span><span class="sxs-lookup"><span data-stu-id="0043c-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="0043c-110">Aunque un grupo de servidores se defina como dos o más equipos con equilibrio de carga, puede crear un grupo de servidores de un solo equipo y un nombre de dominio completo de grupo de servidores para ese único equipo.</span><span class="sxs-lookup"><span data-stu-id="0043c-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="0043c-111">Cuando esté listo para agregar más equipos al grupo más adelante, debe volver a crear el generador de topología para definir el nuevo miembro del grupo, publicar la nueva topología y, a continuación, configurar el nuevo miembro del grupo de conferencias a/V mediante el Asistente para la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0043c-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="0043c-112">Los grupos de servidores de conferencia a/V son únicos, ya que no necesitan equilibradores de carga para crear un grupo.</span><span class="sxs-lookup"><span data-stu-id="0043c-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="0043c-113">Los grupos de conferencia A/V realizan un equilibrio de carga interno y no necesitan hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="0043c-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

