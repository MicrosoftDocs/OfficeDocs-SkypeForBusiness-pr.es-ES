---
title: Quitar instancias y bases de datos de SQL Server en el servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c400fb6e7e206c43a81cdf6b14b2da0d01486447
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="c1857-102">Quitar instancias y bases de datos de SQL Server en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="c1857-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1857-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c1857-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c1857-104">Quite las bases de datos e instancias de Microsoft SQL Server después de quitar los servidores que ejecutan Lync Server 2010 que dependen de ellos, o después de volver a configurar los servidores que ejecutan Lync Server 2010 para usar otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1857-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="c1857-105">Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual que ejecuta Lync Server 2010 de forma que represente las bases de datos obsoletas o no disponibles.</span><span class="sxs-lookup"><span data-stu-id="c1857-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="c1857-106">Para quitar las bases de datos o instancias para el servidor de archivado o el servidor de supervisión, primero debe quitar la función de servidor.</span><span class="sxs-lookup"><span data-stu-id="c1857-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="c1857-107">De forma similar, para quitar las instancias o bases de datos del grupo de servidores front-end, primero debe quitar o volver a configurar la función de servidor dependiente.</span><span class="sxs-lookup"><span data-stu-id="c1857-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="c1857-108">Estos procedimientos no distinguen entre bases de datos combinadas o instancias independientes de los servidores.</span><span class="sxs-lookup"><span data-stu-id="c1857-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="c1857-109">Los procedimientos no se ven afectados por la combinación de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c1857-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c1857-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1857-110">In This Section</span></span>

  - [<span data-ttu-id="c1857-111">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="c1857-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="c1857-112">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="c1857-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="c1857-113">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="c1857-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

