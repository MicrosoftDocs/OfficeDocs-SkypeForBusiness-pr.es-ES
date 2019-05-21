---
title: Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Aprenda a agregar más bases de datos de Skype empresarial Server a un grupo de disponibilidad AlwaysOn existente y obtenga más información sobre los pasos adicionales necesarios después de la revisión o la actualización de un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275188"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="48dc1-103">Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="48dc1-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="48dc1-104">Siga los pasos descritos en este artículo para agregar más bases de datos de Skype empresarial Server a un grupo de disponibilidad AlwaysOn existente en Skype empresarial Server y conocer los pasos adicionales necesarios después de la revisión o actualizar un servidor back-end que forma parte de Grupo disponibilidad en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="48dc1-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="48dc1-105">Agregar bases de datos a un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="48dc1-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="48dc1-106">Abra SQL Server Management Studio y vaya al grupo disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="48dc1-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="48dc1-107">Conmuta por error a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="48dc1-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="48dc1-108">En el generador de topología, establezca el FQDN de SQL Server del grupo de disponibilidad AlwaysOn en el FQDN del nodo principal de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="48dc1-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="48dc1-109">Abra el generador de topologías, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48dc1-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="48dc1-110">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="48dc1-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="48dc1-111">Haga clic con el botón derecho en el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="48dc1-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="48dc1-112">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="48dc1-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="48dc1-113">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="48dc1-113">Publish the topology.</span></span> <span data-ttu-id="48dc1-114">En el menú **Acción**, haga clic en **Topología** y después en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="48dc1-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="48dc1-115">A continuación, en la página de confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="48dc1-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="48dc1-116">Use SQL Server Management Studio para agregar la nueva base de datos al grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="48dc1-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="48dc1-117">Revisar o actualizar un SQL Server en un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="48dc1-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="48dc1-118">Después de revisar un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="48dc1-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="48dc1-119">Instale la actualización en su servidor o servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="48dc1-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="48dc1-120">Ejecute el siguiente comando de PowerShell en el shell de administración de Skype empresarial (sesión iniciada con una cuenta que se ha cometido correctamente para aplicar cambios en las bases de datos de SQL AlwaysOn) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="48dc1-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="48dc1-121">Donde [sqlpool.contoso.com] se reemplaza por el nombre de dominio completo (FQDN) del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="48dc1-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
