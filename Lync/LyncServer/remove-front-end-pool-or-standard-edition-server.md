---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b004426c65157ef7ad1120728c9daeea1b68f161
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="a45f8-102">Quitar un grupo de servidores front-end o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a45f8-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a45f8-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a45f8-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a45f8-104">Este tema le guiará por el proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a45f8-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="a45f8-105">Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo.</span><span class="sxs-lookup"><span data-stu-id="a45f8-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="a45f8-106">Al quitar un servidor front-end Standard Edition, debe quitar la definición del almacén de SQL del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a45f8-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="a45f8-107">Para quitar un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a45f8-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="a45f8-108">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a45f8-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="a45f8-109">Navegue hasta el nodo 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a45f8-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="a45f8-110">Expanda grupos de servidores Front **-End Enterprise Edition**, expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desee quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a45f8-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="a45f8-111">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a45f8-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="a45f8-112">Para quitar un servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a45f8-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="a45f8-113">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a45f8-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="a45f8-114">Navegue hasta el nodo 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a45f8-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="a45f8-115">Expanda **servidores front-end Standard Edition**, haga clic con el botón secundario en el servidor front-end que desea quitar y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a45f8-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="a45f8-116">Expanda **almacenes SQL**, haga clic con el botón secundario en la base de datos de SQL Server asociada con el servidor front-end Standard Edition y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a45f8-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a45f8-117">Debe quitar la definición de las bases de datos de SQL Server combinados del servidor front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a45f8-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="a45f8-118">Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a45f8-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

