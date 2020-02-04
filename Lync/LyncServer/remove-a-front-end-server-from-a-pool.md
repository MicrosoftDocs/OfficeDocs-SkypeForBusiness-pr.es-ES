---
title: Quitar un servidor front-end de un grupo de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="d2242-102">Quitar un servidor front-end de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="d2242-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2242-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d2242-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d2242-104">El servidor front-end de Microsoft Lync Server 2010 Enterprise Edition no puede existir como un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="d2242-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="d2242-105">Debe definirse como un grupo de servidores front-end, incluso si solo hay un equipo en el grupo.</span><span class="sxs-lookup"><span data-stu-id="d2242-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="d2242-106">Este tema le guiará a través del proceso de eliminación de un servidor de front-end individual de un grupo de servidores front-end existente.</span><span class="sxs-lookup"><span data-stu-id="d2242-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="d2242-107">Si el servidor front-end es el último servidor del grupo o si va a quitar el grupo por completo, consulte [quitar grupo de servidores front-end o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2242-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="d2242-108">No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d2242-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="d2242-109">Al quitar el grupo, se quita cada uno de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d2242-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="d2242-110">Para quitar un servidor front-end de un grupo</span><span class="sxs-lookup"><span data-stu-id="d2242-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="d2242-111">Abra el servidor front-end 2013 de Lync Server, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="d2242-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="d2242-112">Vaya al nodo de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2242-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="d2242-113">Expanda **agrupaciones front end de Enterprise Edition**, expanda el grupo de aplicaciones para el usuario con el servidor front-end que desee quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d2242-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

