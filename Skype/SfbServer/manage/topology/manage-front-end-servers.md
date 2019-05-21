---
title: Administrar servidores front-end en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Aprenda a agregar, quitar, aplicar revisiones o actualizar servidores front-end en Skype empresarial Server.'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275160"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="65fb5-103">Administrar servidores front-end en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="65fb5-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="65fb5-104">En este artículo se explica cómo agregar o quitar servidores front-end y cómo aplicar actualizaciones o revisiones a los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="65fb5-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="65fb5-105">Agregar o quitar servidores front-end</span><span class="sxs-lookup"><span data-stu-id="65fb5-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="65fb5-106">Al agregar un servidor front-end a un grupo o quitar un servidor front-end de un grupo, debe reiniciar el grupo.</span><span class="sxs-lookup"><span data-stu-id="65fb5-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="65fb5-p101">Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="65fb5-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="65fb5-110">Puede usar el siguiente procedimiento al agregar o quitar un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="65fb5-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="65fb5-111">Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo.</span><span class="sxs-lookup"><span data-stu-id="65fb5-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="65fb5-112">Para agregar o quitar servidores front-end</span><span class="sxs-lookup"><span data-stu-id="65fb5-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="65fb5-113">Si va a quitar los servidores front-end, primero detenga las conexiones nuevas a esos servidores.</span><span class="sxs-lookup"><span data-stu-id="65fb5-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="65fb5-114">Para ello, puede usar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="65fb5-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="65fb5-115">Abra el generador de topologías y agregue o quite los servidores necesarios.</span><span class="sxs-lookup"><span data-stu-id="65fb5-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="65fb5-116">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="65fb5-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65fb5-p103">Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="65fb5-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="65fb5-120">Además, cuando agregue o quite un servidor a la agrupación, debe ejecutar el Asistente para la implementación de Skype empresarial Server en cada uno de los equipos agregados o eliminados, para obtener más información, consulte [instalar Skype empresarial Server en servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="65fb5-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="65fb5-121">Si ha cambiado el número de servidores en el grupo de servidores front-end de cualquiera de las siguientes maneras, restablezca el grupo con el siguiente cmdlet: RESET-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="65fb5-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="65fb5-122">De 2 a ninguno</span><span class="sxs-lookup"><span data-stu-id="65fb5-122">2 to any</span></span>
    
     - <span data-ttu-id="65fb5-123">De ninguno a 2</span><span class="sxs-lookup"><span data-stu-id="65fb5-123">Any to 2</span></span>
    
     - <span data-ttu-id="65fb5-124">De 3 a ninguno</span><span class="sxs-lookup"><span data-stu-id="65fb5-124">3 to any</span></span>
    
     - <span data-ttu-id="65fb5-125">De ninguno a 3</span><span class="sxs-lookup"><span data-stu-id="65fb5-125">Any to 3</span></span>
    
5. <span data-ttu-id="65fb5-126">Reinicie el grupo al escribir el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="65fb5-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="65fb5-127">Aplicar parches a servidores front-end o actualizarlos</span><span class="sxs-lookup"><span data-stu-id="65fb5-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="65fb5-128">Cuando se revisan los servidores de un grupo de servidores front-end, lo hace de un servidor a la vez.</span><span class="sxs-lookup"><span data-stu-id="65fb5-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="65fb5-129">Para aplicar una actualización a los servidores front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="65fb5-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="65fb5-130">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="65fb5-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="65fb5-131">Si este cmdlet muestra alguna réplica que falte, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier parche:</span><span class="sxs-lookup"><span data-stu-id="65fb5-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="65fb5-132">Ejecute el siguiente cmdlet en el primer servidor al que desee aplicar un parche:</span><span class="sxs-lookup"><span data-stu-id="65fb5-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="65fb5-133">Este cmdlet mueve todos los servicios a otros servidores front-end del grupo y desconecta este servidor.</span><span class="sxs-lookup"><span data-stu-id="65fb5-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="65fb5-134">Aplique la actualización o revisión en el servidor desconectado.</span><span class="sxs-lookup"><span data-stu-id="65fb5-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="65fb5-135">En el servidor actualizado, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="65fb5-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="65fb5-136">El servidor vuelve al servicio.</span><span class="sxs-lookup"><span data-stu-id="65fb5-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="65fb5-137">Repita los pasos 2 a 4 para cada servidor que necesite una actualización.</span><span class="sxs-lookup"><span data-stu-id="65fb5-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
