---
title: Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn y obtenga información sobre los pasos adicionales necesarios después de la revisión o actualizar un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: ca7a792e001c29e087b9b6ac1637029c90ea1ae9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222810"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="35ddd-103">Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="35ddd-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="35ddd-104">Use los pasos de este artículo para agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server y obtenga información acerca de los pasos adicionales necesarios después de una revisión o actualización de un servidor Back-End que forma parte de un AlwaysOn Grupo de disponibilidad en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="35ddd-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="35ddd-105">Agregar las bases de datos a un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="35ddd-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="35ddd-106">Abra SQL Server Management Studio y navegue hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="35ddd-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="35ddd-107">Conmutación por error se a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="35ddd-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="35ddd-108">En el generador de topología, establezca el FQDN del grupo de disponibilidad AlwaysOn de SQL Server en el FQDN del nodo principal de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="35ddd-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="35ddd-109">Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="35ddd-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="35ddd-110">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="35ddd-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="35ddd-111">Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="35ddd-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="35ddd-112">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="35ddd-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="35ddd-113">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="35ddd-113">Publish the topology.</span></span> <span data-ttu-id="35ddd-114">En el menú **Acción**, haga clic en **Topología** y después en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="35ddd-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="35ddd-115">A continuación, en la página de confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="35ddd-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="35ddd-116">Use SQL Server Management Studio para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="35ddd-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="35ddd-117">Una revisión o actualizar un servidor SQL Server en un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="35ddd-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="35ddd-118">Después de la aplicación de revisiones de un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="35ddd-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="35ddd-119">Instalar la actualización en su Skype para Business server o servidores.</span><span class="sxs-lookup"><span data-stu-id="35ddd-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="35ddd-120">Ejecute el siguiente comando de PowerShell en su Skype para Shell de administración de negocio (iniciado la sesión con una cuenta que sea adecuadamente con permisos únicos para aplicar los cambios a las bases de datos de AlwaysOn de SQL) como sigue:</span><span class="sxs-lookup"><span data-stu-id="35ddd-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="35ddd-121">Donde [sqlpool.contoso.com] se sustituye por el nombre de dominio completo (FQDN) de su grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="35ddd-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>