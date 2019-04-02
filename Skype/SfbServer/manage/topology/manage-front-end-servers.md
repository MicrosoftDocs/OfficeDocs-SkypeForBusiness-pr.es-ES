---
title: Administrar servidores Front-End de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Obtenga información sobre cómo agregar, quitar, revisión o actualizar los servidores Front-End en Skype para Business Server.'
ms.openlocfilehash: bfd090ab007523ff05795aff012e4a01da4a0175
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026184"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="1ded8-103">Administrar servidores Front-End de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1ded8-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="1ded8-104">En este artículo se explica cómo agregar o quitar servidores Front-End y cómo aplicar las actualizaciones o revisiones a servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="1ded8-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="1ded8-105">Agregar o quitar servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="1ded8-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="1ded8-106">Al agregar un servidor Front-End a un grupo de servidores, o quitar un servidor Front-End de un grupo de servidores, debe reiniciar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="1ded8-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1ded8-p101">Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="1ded8-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="1ded8-110">Puede usar el siguiente procedimiento al agregar o quitar un servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="1ded8-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ded8-111">Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo.</span><span class="sxs-lookup"><span data-stu-id="1ded8-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="1ded8-112">Para agregar o quitar servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="1ded8-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="1ded8-113">Si va a quitar los servidores Front-End, en primer lugar detenga nuevas conexiones a esos servidores.</span><span class="sxs-lookup"><span data-stu-id="1ded8-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="1ded8-114">Para ello, puede usar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1ded8-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="1ded8-115">Abra el generador de topologías y agregar o quitar los servidores necesarios.</span><span class="sxs-lookup"><span data-stu-id="1ded8-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="1ded8-116">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="1ded8-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1ded8-p103">Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="1ded8-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="1ded8-120">También, al agregar o quitar un servidor al grupo de servidores, debe ejecutar el Skype para el Asistente para la implementación empresarial Server en cada equipo agregado o quitado, para obtener más información, vea [Instalar Skype para Business Server en servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="1ded8-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="1ded8-121">Si ha cambiado el número de servidores en el grupo de servidores Front-End en cualquiera de las siguientes maneras, a continuación, restablecer el grupo de servidores con escribiendo el siguiente cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="1ded8-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="1ded8-122">De 2 a ninguno</span><span class="sxs-lookup"><span data-stu-id="1ded8-122">2 to any</span></span>
    
     - <span data-ttu-id="1ded8-123">De ninguno a 2</span><span class="sxs-lookup"><span data-stu-id="1ded8-123">Any to 2</span></span>
    
     - <span data-ttu-id="1ded8-124">De 3 a ninguno</span><span class="sxs-lookup"><span data-stu-id="1ded8-124">3 to any</span></span>
    
     - <span data-ttu-id="1ded8-125">De ninguno a 3</span><span class="sxs-lookup"><span data-stu-id="1ded8-125">Any to 3</span></span>
    
5. <span data-ttu-id="1ded8-126">Reinicie el grupo al escribir el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="1ded8-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="1ded8-127">Aplicar parches a servidores front-end o actualizarlos</span><span class="sxs-lookup"><span data-stu-id="1ded8-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="1ded8-128">Revisión en los servidores de un grupo de servidores Front-End, se realiza por lo que un servidor a la vez.</span><span class="sxs-lookup"><span data-stu-id="1ded8-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="1ded8-129">Para aplicar una actualización a los servidores front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="1ded8-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="1ded8-130">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1ded8-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="1ded8-131">Si este cmdlet muestra alguna réplica que falte, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier parche:</span><span class="sxs-lookup"><span data-stu-id="1ded8-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="1ded8-132">Ejecute el siguiente cmdlet en el primer servidor al que desee aplicar un parche:</span><span class="sxs-lookup"><span data-stu-id="1ded8-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="1ded8-133">Este cmdlet mueve todos los servicios a otros servidores Front-End del grupo de servidores y desconecta este servidor.</span><span class="sxs-lookup"><span data-stu-id="1ded8-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="1ded8-134">Aplique la actualización o revisión en el servidor desconectado.</span><span class="sxs-lookup"><span data-stu-id="1ded8-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="1ded8-135">En el servidor actualizado, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ded8-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="1ded8-136">El servidor vuelve al servicio.</span><span class="sxs-lookup"><span data-stu-id="1ded8-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="1ded8-137">Repita los pasos 2 a 4 para cada servidor que necesite una actualización.</span><span class="sxs-lookup"><span data-stu-id="1ded8-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
