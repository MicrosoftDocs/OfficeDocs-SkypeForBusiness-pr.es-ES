---
title: Grupo de servidores heredados de la fase 8 de retiro
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: En el siguiente tema se proporcionan instrucciones para actualizar las entradas DNS, mover el servidor de administración de contenido, retirar los grupos de servidores y desactivar y quitar servidores y grupos de servidores de una implementación heredada. No todos los procedimientos de esta sección son obligatorios. Lea la documentación y determine qué procedimiento utilizar.
ms.openlocfilehash: 2406b25436bc13cafca8b09c92220a96e0635ae3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753698"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="545e6-105">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="545e6-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="545e6-106">En el siguiente tema se proporcionan instrucciones para actualizar las entradas DNS, mover el servidor de administración de contenido, retirar los grupos de servidores y desactivar y quitar servidores y grupos de servidores de una implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="545e6-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="545e6-107">No todos los procedimientos de esta sección son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="545e6-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="545e6-108">Lea la documentación y determine qué procedimiento utilizar.</span><span class="sxs-lookup"><span data-stu-id="545e6-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="545e6-109">Para obtener un artículo de una vez, pero exhaustiva, sobre cómo quitar servidores y roles de servidor, y una guía paso a paso para retirar una implementación, descargue [desinstalación de Microsoft Lync Server y quite roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="545e6-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="545e6-110">Para obtener información sobre la migración y actualización de aplicaciones de la API administrada de comunicaciones unificadas de Microsoft (UCMA) antes de retirar el entorno heredado, consulte [escenarios de las aplicaciones de UCMA: coexistencia, migración y actualización](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="545e6-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="545e6-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="545e6-111">In this section</span></span>

> [<span data-ttu-id="545e6-112">Actualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="545e6-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="545e6-113">Mover el servidor de administración central de instalación heredada a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="545e6-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="545e6-114">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="545e6-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="545e6-115">Quitar la asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="545e6-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="545e6-116">Quitar la asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="545e6-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="545e6-117">Quitar el servidor front-end Enterprise Edition o el servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="545e6-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="545e6-118">Quitar instancias de SQL Server y bases de datos en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="545e6-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

