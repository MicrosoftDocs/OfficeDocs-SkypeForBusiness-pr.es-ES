---
title: Quitar un servidor front-end de un grupo de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un equipo en el grupo.
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244298"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c9ef3-104">Quitar un servidor front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="c9ef3-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="c9ef3-105">El servidor front-end no puede existir como un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="c9ef3-106">Debe definirse como un grupo de servidores front-end, incluso si solo hay un equipo en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="c9ef3-107">Este tema le guiará a través del proceso de eliminación de un servidor de front-end individual de un grupo de servidores front-end existente.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="c9ef3-108">Si el servidor front-end es el último servidor del grupo o si va a quitar el grupo por completo, consulte [quitar grupo de servidores front-end o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="c9ef3-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="c9ef3-109">No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="c9ef3-110">Al quitar el grupo, se quita cada uno de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c9ef3-111">Para quitar un servidor front-end de un grupo</span><span class="sxs-lookup"><span data-stu-id="c9ef3-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="c9ef3-112">En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c9ef3-113">Vaya al nodo instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="c9ef3-114">Expanda **agrupaciones front end de Enterprise Edition**, expanda el grupo de aplicaciones para el usuario con el servidor front-end que desee quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c9ef3-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

