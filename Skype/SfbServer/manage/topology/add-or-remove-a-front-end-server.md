---
title: Agregar o quitar un servidor front-end en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Conozca cómo agregar o quitar servidores frontales de Skype para Business Server.'
ms.openlocfilehash: aed52becf5d4cc97307f9788a81f8d6563d1d25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d1ca7-103">Agregar o quitar un servidor front-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d1ca7-103">Add or remove a Front End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1ca7-104">**Resumen:** Aprenda a agregar o quitar servidores frontales de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="d1ca7-105">Cuando agregue un servidor Front-End a un grupo, o quitar un servidor Front-End de un grupo, debe reiniciar el grupo.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d1ca7-p101">Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="d1ca7-109">Puede utilizar el procedimiento siguiente al agregar o quitar un servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1ca7-110">Si agrega nuevos servidores al grupo, actualice los nuevos servidores del grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes del grupo.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="d1ca7-111">Para agregar o quitar servidores frontales</span><span class="sxs-lookup"><span data-stu-id="d1ca7-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="d1ca7-112">Si desea quitar los servidores frontales, detener nuevas conexiones a los servidores.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="d1ca7-113">Para ello, puede usar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d1ca7-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="d1ca7-114">Abrir el generador de topología y agregar o quitar los servidores necesarios.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="d1ca7-115">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d1ca7-p103">Cuando agregue o quite un servidor de un grupo en su topología y después publique la topología actualizada, todos los servidores del grupo se reiniciarán al mismo tiempo. Mientras se reinician los servidores, el grupo está sin conexión, lo que interrumpirá el servicio para aquellos usuarios que estén conectados a dicho grupo. Para evitar cualquier interrupción de servicio para los usuarios, planifique que la publicación de la topología con el nuevo servidor del grupo se lleve a cabo durante el horario no comercial.</span><span class="sxs-lookup"><span data-stu-id="d1ca7-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="d1ca7-119">Si ha cambiado el número de servidores en el grupo de servidores Front-End en cualquiera de las siguientes formas, restablecer el fondo con escribiendo el siguiente cmdlet: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="d1ca7-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="d1ca7-120">De 2 a ninguno</span><span class="sxs-lookup"><span data-stu-id="d1ca7-120">2 to any</span></span>
    
     - <span data-ttu-id="d1ca7-121">De ninguno a 2</span><span class="sxs-lookup"><span data-stu-id="d1ca7-121">Any to 2</span></span>
    
     - <span data-ttu-id="d1ca7-122">De 3 a ninguno</span><span class="sxs-lookup"><span data-stu-id="d1ca7-122">3 to any</span></span>
    
     - <span data-ttu-id="d1ca7-123">De ninguno a 3</span><span class="sxs-lookup"><span data-stu-id="d1ca7-123">Any to 3</span></span>
    
5. <span data-ttu-id="d1ca7-124">Reinicie el grupo al escribir el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="d1ca7-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```


