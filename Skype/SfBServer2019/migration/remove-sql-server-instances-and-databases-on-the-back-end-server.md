---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quitar las bases de datos de Microsoft SQL Server y sesiones después de quitar los servidores que ejecutan son dependientes en ellos, o después de volver a configurar los servidores para usar otra base de datos. Debe realizar el procedimiento de este tema al retirar la versión actual de SQL Server o volver a configurar el servidor actual de forma que se representa las bases de datos obsoletos o no está disponible.
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898743"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="f9cfe-104">Quitar instancias de SQL Server y bases de datos en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="f9cfe-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="f9cfe-105">Quitar las bases de datos de Microsoft SQL Server y sesiones después de quitar los servidores que ejecutan son dependientes en ellos, o después de volver a configurar los servidores para usar otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9cfe-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="f9cfe-106">Debe realizar el procedimiento de este tema al retirar la versión actual de SQL Server o volver a configurar el servidor actual de forma que se representa las bases de datos obsoletos o no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f9cfe-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="f9cfe-107">Para quitar las bases de datos o instancias para el servidor de archivado o el servidor de supervisión, primero debe quitar el rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="f9cfe-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="f9cfe-108">De forma similar, para quitar las instancias o las bases de datos para el grupo de servidores Front-End, primero debe quitar o volver a configurar el rol de servidor dependientes.</span><span class="sxs-lookup"><span data-stu-id="f9cfe-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="f9cfe-109">Estos procedimientos no realizar ninguna distinción entre bases de datos combinadas o separada para los servidores.</span><span class="sxs-lookup"><span data-stu-id="f9cfe-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="f9cfe-110">Los procedimientos se ven afectados por la combinación de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f9cfe-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f9cfe-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f9cfe-111">In this section</span></span>

- [<span data-ttu-id="f9cfe-112">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f9cfe-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="f9cfe-113">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="f9cfe-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="f9cfe-114">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="f9cfe-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

