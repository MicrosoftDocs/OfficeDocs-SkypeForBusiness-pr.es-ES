---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
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
description: Este tema le guiará por el proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo. Al quitar un servidor front-end Standard Edition, debe quitar la definición del almacén de SQL del generador de topologías.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752282"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="5826e-105">Quitar un grupo de servidores front-end o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5826e-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="5826e-106">Este artículo le guiará por el proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5826e-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="5826e-107">Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo.</span><span class="sxs-lookup"><span data-stu-id="5826e-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="5826e-108">Al quitar un servidor front-end Standard Edition, debe quitar la definición del almacén de SQL del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="5826e-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="5826e-109">Para quitar un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5826e-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="5826e-110">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="5826e-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="5826e-111">Desplácese hasta el nodo heredado.</span><span class="sxs-lookup"><span data-stu-id="5826e-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="5826e-112">Expanda grupos de servidores Front **-End Enterprise Edition**, expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5826e-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="5826e-113">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación heredada según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5826e-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="5826e-114">Para quitar un servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5826e-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="5826e-115">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="5826e-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="5826e-116">Navegue hasta el nodo instalaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="5826e-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="5826e-117">Expanda **servidores front-end Standard Edition**, haga clic con el botón secundario en el servidor front-end que desea quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5826e-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="5826e-118">Expanda **almacenes SQL**, haga clic con el botón secundario en la base de datos de SQL Server asociada con el servidor front-end Standard Edition y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5826e-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5826e-119">Debe quitar la definición de las bases de datos de SQL Server combinados del servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5826e-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="5826e-120">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5826e-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

