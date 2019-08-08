---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tema le guiará a través del proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quita cada servidor front-end que pertenece al grupo como parte del proceso de eliminación de la agrupación. Al quitar un servidor front-end Standard Edition, debe quitar la definición de la tienda SQL del generador de topología.
ms.openlocfilehash: 57679fb248c9281b79c12be98b7fd5246c9afd38
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244270"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="571e9-105">Quitar un grupo de servidores front-end o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="571e9-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="571e9-106">Este artículo le guiará a través del proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="571e9-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="571e9-107">Al quitar un grupo de servidores front-end, se quita cada servidor front-end que pertenece al grupo como parte del proceso de eliminación de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="571e9-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="571e9-108">Al quitar un servidor front-end Standard Edition, debe quitar la definición de la tienda SQL del generador de topología.</span><span class="sxs-lookup"><span data-stu-id="571e9-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="571e9-109">Para quitar un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="571e9-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="571e9-110">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="571e9-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="571e9-111">Vaya al nodo heredado.</span><span class="sxs-lookup"><span data-stu-id="571e9-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="571e9-112">Expanda agrupaciones **front end de Enterprise Edition**, expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="571e9-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="571e9-113">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación heredada según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="571e9-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="571e9-114">Para quitar un servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="571e9-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="571e9-115">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="571e9-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="571e9-116">Vaya al nodo instalaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="571e9-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="571e9-117">Expanda **servidores front-end Standard Edition**, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="571e9-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="571e9-118">Expanda **almacenes SQL**, haga clic con el botón secundario en la base de datos de SQL Server asociada al servidor front-end Standard Edition y, después, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="571e9-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="571e9-119">Debe quitar la definición de las bases de datos de SQL Server en el servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="571e9-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="571e9-120">Publique la topología, compruebe el estado de la replicación y, a continuación, ejecute el Asistente para la implementación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="571e9-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

