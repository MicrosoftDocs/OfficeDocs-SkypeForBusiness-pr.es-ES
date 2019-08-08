---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede quitar las bases de datos y las instancias de Microsoft SQL Server después de quitar los servidores que dependen de ellos o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual de modo tal que represente las bases de datos obsoletas o no disponibles.
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244204"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="96e10-104">Quitar instancias de SQL Server y bases de datos en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="96e10-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="96e10-105">Puede quitar las bases de datos y las instancias de Microsoft SQL Server después de quitar los servidores que dependen de ellos o después de volver a configurar los servidores para que usen otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="96e10-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="96e10-106">Debe realizar el procedimiento de este tema cuando retire el servidor SQL Server actual o vuelva a configurar el servidor actual de modo tal que represente las bases de datos obsoletas o no disponibles.</span><span class="sxs-lookup"><span data-stu-id="96e10-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="96e10-107">Para quitar las bases de datos o instancias del servidor de archivado o del servidor de supervisión, primero debe quitar el rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="96e10-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="96e10-108">De forma similar, para quitar las instancias o bases de datos de un grupo de servidores front-end, primero debe quitar o volver a configurar la función de servidor dependiente.</span><span class="sxs-lookup"><span data-stu-id="96e10-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="96e10-109">Estos procedimientos no hacen distinción entre bases de datos colocadas o instancias independientes para servidores.</span><span class="sxs-lookup"><span data-stu-id="96e10-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="96e10-110">Los procedimientos no se ven afectados por la collocation de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="96e10-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="96e10-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="96e10-111">In this section</span></span>

- [<span data-ttu-id="96e10-112">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="96e10-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="96e10-113">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="96e10-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="96e10-114">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="96e10-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

