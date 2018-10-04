---
title: Fase 8 retiro de grupos de servidores heredados
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: El siguiente tema proporciona instrucciones para actualizar las entradas DNS, mover el servidor de administración de contenido, retirar grupos y desactivar y quitar servidores y grupos de servidores de una implementación heredada. No todos los procedimientos enumerados en esta sección son necesarios. Leer la documentación y determine qué procedimiento cómo dar de baja para usar.
ms.openlocfilehash: 0e5c7bebeb0449f8fa71942f2ac68ff9d7eb017a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370763"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="46ab9-105">Fase 8: Retirar grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="46ab9-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="46ab9-106">El siguiente tema proporciona instrucciones para actualizar las entradas DNS, mover el servidor de administración de contenido, retirar grupos y desactivar y quitar servidores y grupos de servidores de una implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="46ab9-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="46ab9-107">No todos los procedimientos enumerados en esta sección son necesarios.</span><span class="sxs-lookup"><span data-stu-id="46ab9-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="46ab9-108">Leer la documentación y determine qué procedimiento cómo dar de baja para usar.</span><span class="sxs-lookup"><span data-stu-id="46ab9-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="46ab9-109">Para un artículo con fecha pero exhaustivo acerca de cómo quitar servidores y roles de servidor y una guía paso a paso para retirar una implementación, descargue la [desinstalación de Microsoft Lync Server y quitar Roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="46ab9-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="46ab9-110">Para obtener información sobre la migración y actualización de aplicaciones de Microsoft Unified Communications Managed API (UCMA), antes de retirar el entorno heredado, consulte [aplicaciones UCMA: escenarios de actualización, migración y coexistencia](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="46ab9-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="46ab9-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="46ab9-111">In this section</span></span>

> [<span data-ttu-id="46ab9-112">Actualizar los registros DNS SRV</span><span class="sxs-lookup"><span data-stu-id="46ab9-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="46ab9-113">Mover el servidor de Administración Central de instalación heredada a Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="46ab9-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="46ab9-114">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="46ab9-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="46ab9-115">Quitar la asociación del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="46ab9-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="46ab9-116">Quitar la asociación del servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="46ab9-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="46ab9-117">Quitar el servidor Front-End Enterprise Edition o servidor Front-End de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="46ab9-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="46ab9-118">Quitar instancias de SQL Server y bases de datos en el servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="46ab9-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

