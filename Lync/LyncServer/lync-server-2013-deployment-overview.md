---
title: 'Lync Server 2013: Introducción general a la implementación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="80744-102">Introducción general a la implementación para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80744-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80744-103">_**Última modificación del tema:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="80744-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="80744-104">La principal diferencia entre Lync Server 2013 Enterprise Edition y Lync Server 2013 Standard es que Standard Edition no es compatible con las características de alta disponibilidad incluidas en Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="80744-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="80744-105">Para una alta disponibilidad, necesita implementar varios servidores front-end en un grupo y, a continuación, puede reflejar el servidor que ejecuta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="80744-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="80744-106">Con Enterprise Edition puede elegir Collocate o definir un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="80744-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="80744-107">El servidor de supervisión y el servidor de archivado pueden usar un servidor independiente que ejecute SQL Server.</span><span class="sxs-lookup"><span data-stu-id="80744-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="80744-108">O bien, pueden tener instancias de SQL Server ejecutándose en el servidor de bases de datos para los servidores y los grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="80744-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="80744-109">Los servidores que ejecutan Lync Server 2013 Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas, que se han quitado geográficamente de la implementación principal de la organización.</span><span class="sxs-lookup"><span data-stu-id="80744-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="80744-110">Dos servidores de servidor Standard Edition acoplados para conmutación por error en caso de desastre pueden admitir hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="80744-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="80744-111">No puede agrupar servidores Standard Edition como servidores front-end en Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="80744-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="80744-112">Además, la base de datos de SQL Server que usa Standard Edition es un servidor en el que se ejecuta SQL Server Express diseñado para controlar las cargas de trabajo de los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="80744-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="80744-113">Esto no quiere decir que todos los roles deben residir en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="80744-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="80744-114">Puede tener servidores de mediación y servidores perimetrales independientes.</span><span class="sxs-lookup"><span data-stu-id="80744-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="80744-115">La base de datos de SQL Server para el almacén de administración central y para los fines de Lync Server 2013 debe residir en el servidor Standard Edition, que se encuentra en el servidor que ejecuta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="80744-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="80744-116">El servidor de supervisión y el servidor de archivado usan un servidor independiente con la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="80744-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

