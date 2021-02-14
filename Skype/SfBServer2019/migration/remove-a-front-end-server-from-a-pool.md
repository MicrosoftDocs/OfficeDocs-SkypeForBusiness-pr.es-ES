---
title: Quitar un servidor front-end de un grupo de servidores
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
description: El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un único equipo en el grupo.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752322"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="f46bb-104">Quitar un servidor front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f46bb-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="f46bb-105">El servidor front-end no puede existir como un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="f46bb-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="f46bb-106">Debe definirse como un grupo de servidores front-end, incluso si solo hay un único equipo en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f46bb-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="f46bb-107">En este tema se explica el proceso de eliminación de un servidor front-end individual de un grupo de servidores front-end existente.</span><span class="sxs-lookup"><span data-stu-id="f46bb-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="f46bb-108">Si el servidor front-end es el último servidor del grupo o si va a quitar el grupo por completo, vea Quitar grupo de servidores [front-end o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="f46bb-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="f46bb-109">No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f46bb-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="f46bb-110">Al quitar el grupo de servidores, se quita cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f46bb-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="f46bb-111">Para quitar un servidor front-end de un grupo</span><span class="sxs-lookup"><span data-stu-id="f46bb-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="f46bb-112">En el servidor front-end de Skype Empresarial Server 2019, abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="f46bb-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="f46bb-113">Navegue al nodo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="f46bb-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="f46bb-114">Expanda grupos de servidores **front-end Enterprise Edition,** expanda el grupo de servidores front-end con el servidor front-end que desea quitar, haga clic con el botón secundario en el servidor front-end que desea quitar y, a continuación, haga clic en Eliminar **.**</span><span class="sxs-lookup"><span data-stu-id="f46bb-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

