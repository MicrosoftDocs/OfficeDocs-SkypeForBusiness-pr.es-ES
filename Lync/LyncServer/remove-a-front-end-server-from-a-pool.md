---
title: Quitar un servidor front-end de un grupo de servidores
description: Quitar un servidor front-end de un grupo de servidores.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551306"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="0918c-103">Quitar un servidor front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="0918c-103">Remove a Front End Server from a pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0918c-104">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0918c-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0918c-105">El servidor front-end de Microsoft Lync Server 2010 Enterprise Edition no puede existir como un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="0918c-105">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="0918c-106">Debe definirse como un grupo de servidores front-end, incluso si hay un solo equipo en el grupo.</span><span class="sxs-lookup"><span data-stu-id="0918c-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="0918c-107">Este tema le guiará por el proceso de eliminación de un servidor front-end individual de un grupo de servidores front-end existente.</span><span class="sxs-lookup"><span data-stu-id="0918c-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="0918c-108">Si el servidor front-end es el último servidor del grupo o si va a quitar completamente el grupo de servidores, consulte [quitar un grupo de servidores front-end o un servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="0918c-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="0918c-109">No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0918c-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="0918c-110">Al quitar el grupo de servidores, se quitan todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0918c-110">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="0918c-111">Para quitar un servidor front-end de un grupo</span><span class="sxs-lookup"><span data-stu-id="0918c-111">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="0918c-112">Abra el servidor front-end de Lync Server 2013 y abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="0918c-112">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="0918c-113">Navegue hasta el nodo 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0918c-113">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="0918c-114">Expanda grupos de servidores Front **-End Enterprise Edition**, expanda el grupo de servidores front-end con el servidor front-end que desea quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0918c-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

