---
title: Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn y obtenga información sobre los pasos adicionales necesarios después de la revisión o actualizar un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: 07aaadc303063204cef4a5561a83ec71b629c21b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911934"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="32a4d-103">Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32a4d-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="32a4d-104">Use los pasos de este artículo para agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server y obtenga información acerca de los pasos adicionales necesarios después de una revisión o actualización de un servidor Back-End que forma parte de un AlwaysOn Grupo de disponibilidad en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="32a4d-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="32a4d-105">Agregar las bases de datos a un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="32a4d-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="32a4d-106">Abra SQL Server Management Studio y navegue hasta el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="32a4d-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="32a4d-107">Conmutación por error se a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="32a4d-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="32a4d-108">En el generador de topología, establezca el FQDN del grupo de disponibilidad AlwaysOn de SQL Server en el FQDN del nodo principal de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="32a4d-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="32a4d-109">Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32a4d-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="32a4d-110">Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="32a4d-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="32a4d-111">Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="32a4d-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="32a4d-112">En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="32a4d-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="32a4d-113">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="32a4d-113">Publish the topology.</span></span> <span data-ttu-id="32a4d-114">En el menú **Acción**, haga clic en **Topología** y después en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="32a4d-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="32a4d-115">A continuación, en la página de confirmación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32a4d-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="32a4d-116">Use SQL Server Management Studio para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="32a4d-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="32a4d-117">Una revisión o actualizar un servidor SQL Server en un grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="32a4d-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="32a4d-118">Después de la aplicación de revisiones de un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="32a4d-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="32a4d-119">Instalar la actualización en su Skype para Business server o servidores.</span><span class="sxs-lookup"><span data-stu-id="32a4d-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="32a4d-120">Ejecute el siguiente comando de PowerShell en su Skype para Shell de administración de negocio (iniciado la sesión con una cuenta que sea adecuadamente con permisos únicos para aplicar los cambios a las bases de datos de AlwaysOn de SQL) como sigue:</span><span class="sxs-lookup"><span data-stu-id="32a4d-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="32a4d-121">Donde [sqlpool.contoso.com] se sustituye por el nombre de dominio completo (FQDN) de su grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="32a4d-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
