---
title: Agregar bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Conozca cómo agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn en Skype para Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="d3044-103">Agregar bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3044-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3044-104">**Resumen:** Aprenda a agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3044-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server 2015.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="d3044-105">Agregar bases de datos a un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="d3044-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="d3044-106">Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d3044-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="d3044-107">Conmutarla a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="d3044-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="d3044-108">Generador de topología, establezca el nombre completo de SQL Server del grupo de disponibilidad AlwaysOn en el FQDN del nodo principal de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="d3044-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="d3044-109">Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d3044-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="d3044-110">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d3044-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d3044-111">(Ratón) en el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d3044-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="d3044-112">En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="d3044-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="d3044-p103">Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3044-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="d3044-116">Para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn, utilice SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d3044-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

