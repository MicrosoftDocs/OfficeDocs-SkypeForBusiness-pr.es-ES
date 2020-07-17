---
title: Administración de servidores front-end en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Obtenga información sobre cómo agregar, quitar, aplicar revisiones o actualizar los servidores front-end en Skype empresarial Server.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098418"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="5406a-103">Administración de servidores front-end en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5406a-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="5406a-104">En este artículo se explica cómo agregar o quitar servidores front-end y cómo aplicar actualizaciones o revisiones a los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="5406a-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="5406a-105">Skype empresarial Server 2019 no es compatible con grupos de servidores front-end Enterprise Edition con dos servidores front-end y no permite que la topología se publique en ese escenario.</span><span class="sxs-lookup"><span data-stu-id="5406a-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="5406a-106">Agregar o quitar servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5406a-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="5406a-107">Cuando agrega un servidor front-end a un grupo o cuando quita un servidor front-end de un grupo, debe reiniciar el grupo.</span><span class="sxs-lookup"><span data-stu-id="5406a-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5406a-108">Al agregar o quitar un servidor del grupo de servidores de la topología y, a continuación, publicar la topología actualizada, se reiniciarán todos los servidores del grupo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5406a-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="5406a-109">Mientras los servidores se reinician, el grupo de servidores está sin conexión, lo que interrumpirá el servicio para los usuarios conectados a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="5406a-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="5406a-110">Para evitar cualquier interrupción del servicio a los usuarios, planee publicar la topología con el nuevo servidor en el grupo de servidores durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="5406a-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="5406a-111">Puede usar el siguiente procedimiento al agregar o quitar un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5406a-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5406a-112">Si va a agregar nuevos servidores al grupo, actualice los nuevos servidores de grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes en el grupo.</span><span class="sxs-lookup"><span data-stu-id="5406a-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="5406a-113">Para agregar o quitar servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5406a-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="5406a-p102">Si desea quitar servidores front-end, primero detenga las nuevas conexiones a esos servidores. Para ello, puede usar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5406a-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="5406a-116">Abra el Generador de topologías, y agregue o quite los servidores necesarios.</span><span class="sxs-lookup"><span data-stu-id="5406a-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="5406a-117">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="5406a-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5406a-118">Al agregar o quitar un servidor del grupo de servidores de la topología y, a continuación, publicar la topología actualizada, se reiniciarán todos los servidores del grupo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5406a-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="5406a-119">Mientras los servidores se reinician, el grupo de servidores está sin conexión, lo que interrumpirá el servicio para los usuarios conectados a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="5406a-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="5406a-120">Para evitar cualquier interrupción del servicio a los usuarios, planee publicar la topología con el nuevo servidor en el grupo de servidores durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="5406a-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="5406a-121">Además, al agregar o quitar un servidor del grupo, debe ejecutar el Asistente para la implementación de Skype empresarial Server en cada equipo que se haya agregado o quitado, para obtener más información, consulte [instalar Skype empresarial Server en los servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="5406a-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="5406a-122">Si ha cambiado el número de servidores en el grupo de servidores front-end de cualquiera de las siguientes maneras, restablezca el grupo con el siguiente cmdlet: RESET-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="5406a-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="5406a-123">2 a cualquier</span><span class="sxs-lookup"><span data-stu-id="5406a-123">2 to any</span></span>
    
     - <span data-ttu-id="5406a-124">De uno a dos</span><span class="sxs-lookup"><span data-stu-id="5406a-124">Any to 2</span></span>
    
     - <span data-ttu-id="5406a-125">3 a cualquier</span><span class="sxs-lookup"><span data-stu-id="5406a-125">3 to any</span></span>
    
     - <span data-ttu-id="5406a-126">De uno a tres</span><span class="sxs-lookup"><span data-stu-id="5406a-126">Any to 3</span></span>
    
5. <span data-ttu-id="5406a-127">Reinicie el grupo de servidores; para ello, escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="5406a-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="5406a-128">Revisión o actualización de los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5406a-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="5406a-129">Cuando se revisan los servidores de un grupo de servidores front-end, lo hace en un servidor cada vez.</span><span class="sxs-lookup"><span data-stu-id="5406a-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="5406a-130">Para aplicar una actualización a los servidores front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="5406a-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="5406a-131">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5406a-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="5406a-132">Si este cmdlet muestra las réplicas que faltan, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier revisión.</span><span class="sxs-lookup"><span data-stu-id="5406a-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="5406a-133">En el primer servidor que quiera revisar, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5406a-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="5406a-134">Este cmdlet mueve todos los servicios a otros servidores front-end del grupo y desconecta el servidor.</span><span class="sxs-lookup"><span data-stu-id="5406a-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="5406a-135">Aplique la actualización o la revisión a este servidor.</span><span class="sxs-lookup"><span data-stu-id="5406a-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="5406a-136">En el servidor actualizado, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5406a-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="5406a-137">El servidor se devuelve al servicio.</span><span class="sxs-lookup"><span data-stu-id="5406a-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="5406a-138">Repita los pasos 2-4 para cada servidor que deba actualizarse.</span><span class="sxs-lookup"><span data-stu-id="5406a-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
