---
title: Quitar un servidor front-end de un grupo de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: El servidor Front-End no puede existir como un equipo independiente. Debe definirse como un grupo de servidores Front-End, incluso si hay un único equipo en el grupo de servidores.
ms.openlocfilehash: f026570f0dff377ba7ca0c28975a685e236a9e13
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231433"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="bb4bd-104">Quitar un servidor front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="bb4bd-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="bb4bd-105">El servidor Front-End no puede existir como un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="bb4bd-106">Debe definirse como un grupo de servidores Front-End, incluso si hay un único equipo en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="bb4bd-107">En este tema le guiará en el proceso de eliminación de un servidor individual de Front-End de un grupo de servidores Front-End existente.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="bb4bd-108">Si el servidor Front-End es el último servidor del grupo de servidores o si va a quitar por completo el grupo de servidores, vea [servidor Standard Edition o grupo de servidores quitar Front-End](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb4bd-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="bb4bd-109">No es necesario para quitar el servidor front-end individuales antes de quitar el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="bb4bd-110">Al quitar el grupo de servidores, quite cada servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="bb4bd-111">Para quitar un servidor Front-End de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="bb4bd-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="bb4bd-112">En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="bb4bd-113">Navegue hasta el nodo instalar heredado.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="bb4bd-114">Expanda **grupos de servidores Front-End de Enterprise Edition**, expanda el grupo de servidores Front-End con el servidor Front-End que desea quitar, haga clic en el servidor Front-End que desea quitar y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bb4bd-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

