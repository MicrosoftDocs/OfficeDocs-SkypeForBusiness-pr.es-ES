---
title: Quitar instancias de SQL Server y bases de datos en el servidor back-end
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
description: Las bases Microsoft SQL Server de datos y las instancias se quitan después de quitar los servidores que dependen de ellas o después de volver a configurar los servidores para que usen otra base de datos. Debe realizar el procedimiento descrito en este tema cuando retire el SQL Server actual o vuelva a configurar el servidor actual de modo que las bases de datos queden obsoletas o no disponibles.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752162"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="d94d5-104">Quitar instancias de SQL Server y bases de datos en el servidor back-end</span><span class="sxs-lookup"><span data-stu-id="d94d5-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="d94d5-105">Las bases Microsoft SQL Server de datos y las instancias se quitan después de quitar los servidores que dependen de ellas o después de volver a configurar los servidores para que usen otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="d94d5-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="d94d5-106">Debe realizar el procedimiento descrito en este tema cuando retire el SQL Server actual o vuelva a configurar el servidor actual de modo que las bases de datos queden obsoletas o no disponibles.</span><span class="sxs-lookup"><span data-stu-id="d94d5-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="d94d5-107">Para quitar las bases de datos o instancias del servidor de archivado o del servidor de supervisión, primero debe quitar el rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="d94d5-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="d94d5-108">Del mismo modo, para quitar las instancias o bases de datos del grupo de servidores front-end, primero debe quitar o volver a configurar el rol de servidor dependiente.</span><span class="sxs-lookup"><span data-stu-id="d94d5-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="d94d5-109">Estos procedimientos no distinguen entre bases de datos combinadas o instancias independientes de los servidores.</span><span class="sxs-lookup"><span data-stu-id="d94d5-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="d94d5-110">Los procedimientos no se ven afectados por la combinación de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d94d5-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d94d5-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d94d5-111">In this section</span></span>

- [<span data-ttu-id="d94d5-112">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="d94d5-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="d94d5-113">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="d94d5-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="d94d5-114">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="d94d5-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

