---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema le guiará en el proceso de eliminación de un grupo de servidores Front-End o un servidor estándar de edición de Front-End. Al quitar un grupo de servidores Front-End, quite cada servidor Front-End que pertenece al grupo de servidores como parte del proceso de eliminación de grupo de servidores. Cuando se quita una edición Standard servidor Front-End, debe quitar la definición de almacén SQL del generador.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872720"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="ab25a-105">Quitar un grupo de servidores front-end o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ab25a-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="ab25a-106">En este artículo le guiará por el proceso de eliminación de un grupo de servidores Front-End o un servidor estándar de edición de Front-End.</span><span class="sxs-lookup"><span data-stu-id="ab25a-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="ab25a-107">Al quitar un grupo de servidores Front-End, quite cada servidor Front-End que pertenece al grupo de servidores como parte del proceso de eliminación de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ab25a-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="ab25a-108">Cuando se quita una edición Standard servidor Front-End, debe quitar la definición de almacén SQL del generador.</span><span class="sxs-lookup"><span data-stu-id="ab25a-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="ab25a-109">Para quitar un grupo de servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ab25a-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="ab25a-110">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ab25a-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ab25a-111">Vaya al nodo heredado.</span><span class="sxs-lookup"><span data-stu-id="ab25a-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="ab25a-112">Expanda **grupos de servidores Front-End de Enterprise Edition**, expanda el grupo de servidores Front-End, haga clic en el grupo de servidores Front-End que desea quitar y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ab25a-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="ab25a-113">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute al Asistente para la implementación heredada según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ab25a-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="ab25a-114">Para quitar un servidor Front-End de Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ab25a-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="ab25a-115">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ab25a-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ab25a-116">Desplácese hasta el nodo de instalaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="ab25a-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="ab25a-117">Expanda **servidores Front-End de Standard Edition**, haga clic en el servidor Front-End que desea quitar y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ab25a-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="ab25a-118">Expanda **almacenes SQL**, haga clic en la base de datos de SQL Server que está asociada con la edición Standard servidor Front-End y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ab25a-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ab25a-119">Debe quitar la definición de las bases de datos de SQL Server instaladas de la edición Standard servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="ab25a-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="ab25a-120">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute al Asistente para la implementación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ab25a-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

