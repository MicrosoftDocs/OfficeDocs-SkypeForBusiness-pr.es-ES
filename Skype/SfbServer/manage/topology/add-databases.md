---
title: Agregar las bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server.'
ms.openlocfilehash: f055466788494f10575b7bd3710705a138c456b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976327"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="e0f68-103">Agregar las bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e0f68-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="e0f68-104">**Resumen:** Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e0f68-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="e0f68-105">Adición de bases de datos a un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="e0f68-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="e0f68-106">Abra SQL Server Management Studio y navegue hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e0f68-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="e0f68-107">Conmutación por error se a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e0f68-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="e0f68-108">En el generador de topología, establezca el FQDN del grupo de disponibilidad AlwaysOn de SQL Server en el FQDN del nodo principal de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="e0f68-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="e0f68-109">Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0f68-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="e0f68-110">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e0f68-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e0f68-111">Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e0f68-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="e0f68-112">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e0f68-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="e0f68-p103">Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e0f68-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="e0f68-116">Use SQL Server Management Studio para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e0f68-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

