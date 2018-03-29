---
title: Aplicar parches a servidores front-end o actualizarlos en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Resumen: Conozca cómo aplicar actualizaciones o revisiones a servidores frontales en Skype para Business Server.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a><span data-ttu-id="24cc2-103">Aplicar parches a servidores front-end o actualizarlos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="24cc2-103">Patch or update Front End Servers in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24cc2-104">**Resumen:** obtener información sobre cómo aplicar actualizaciones o revisiones a servidores frontales en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="24cc2-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="24cc2-105">Cuando la revisión en los servidores de un grupo de servidores Front-End, hacer por lo que un servidor en un momento.</span><span class="sxs-lookup"><span data-stu-id="24cc2-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="24cc2-106">Para aplicar una actualización a los servidores front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="24cc2-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="24cc2-107">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="24cc2-107">Type the following cmdlet:</span></span>
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     <span data-ttu-id="24cc2-108">Si este cmdlet muestra alguna réplica que falte, ejecute el siguiente cmdlet para recuperar el grupo antes de aplicar cualquier parche:</span><span class="sxs-lookup"><span data-stu-id="24cc2-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. <span data-ttu-id="24cc2-109">Ejecute el siguiente cmdlet en el primer servidor al que desee aplicar un parche:</span><span class="sxs-lookup"><span data-stu-id="24cc2-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="24cc2-110">Este cmdlet mueve todos los servicios a otros servidores frontales en la agrupación y desconecta este servidor.</span><span class="sxs-lookup"><span data-stu-id="24cc2-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="24cc2-111">Aplique la actualización o revisión en el servidor desconectado.</span><span class="sxs-lookup"><span data-stu-id="24cc2-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="24cc2-112">En el servidor actualizado, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="24cc2-112">On the upgraded server, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="24cc2-113">El servidor vuelve al servicio.</span><span class="sxs-lookup"><span data-stu-id="24cc2-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="24cc2-114">Repita los pasos 2 a 4 para cada servidor que necesite una actualización.</span><span class="sxs-lookup"><span data-stu-id="24cc2-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

