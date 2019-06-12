---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="34df5-102">Quitar instancias de SQL Server y bases de datos en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="34df5-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34df5-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="34df5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="34df5-104">Puede quitar las bases de datos y las instancias de Microsoft SQL Server después de quitar los servidores que ejecutan Lync Server 2010 que dependen de ellos o después de volver a configurar los servidores que ejecutan Lync Server 2010 para usar otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="34df5-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="34df5-105">Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual que ejecuta Lync Server 2010 de tal forma que represente las bases de datos obsoletas o no disponibles.</span><span class="sxs-lookup"><span data-stu-id="34df5-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="34df5-106">Para quitar las bases de datos o instancias del servidor de archivado o del servidor de supervisión, primero debe quitar el rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="34df5-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="34df5-107">De forma similar, para quitar las instancias o bases de datos de un grupo de servidores front-end, primero debe quitar o volver a configurar la función de servidor dependiente.</span><span class="sxs-lookup"><span data-stu-id="34df5-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="34df5-108">Estos procedimientos no hacen distinción entre bases de datos colocadas o instancias independientes para servidores.</span><span class="sxs-lookup"><span data-stu-id="34df5-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="34df5-109">Los procedimientos no se ven afectados por la collocation de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="34df5-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="34df5-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="34df5-110">In This Section</span></span>

  - [<span data-ttu-id="34df5-111">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="34df5-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="34df5-112">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="34df5-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="34df5-113">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="34df5-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

