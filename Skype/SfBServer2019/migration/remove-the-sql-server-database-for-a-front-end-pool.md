---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
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
description: Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753412"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="70c96-104">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="70c96-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="70c96-105">Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="70c96-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="70c96-106">Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="70c96-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="70c96-107">Para quitar la base de datos de SQL Server mediante el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="70c96-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="70c96-108">Desde el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías y descargue la topología existente.</span><span class="sxs-lookup"><span data-stu-id="70c96-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="70c96-109">En el generador de topologías, vaya a **componentes compartidos** y a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el grupo de servidores front-end quitado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="70c96-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="70c96-110">Publique la topología y compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="70c96-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="70c96-111">Para quitar las bases de datos de usuario y de aplicación del servidor SQL Server</span><span class="sxs-lookup"><span data-stu-id="70c96-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="70c96-112">Para quitar las bases de datos de SQL Server, debe ser miembro del grupo sysadmins de SQL Server para el servidor SQL Server en el que va a quitar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="70c96-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="70c96-113">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="70c96-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="70c96-114">Para quitar la base de datos correspondiente al almacén de usuarios del grupo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70c96-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="70c96-115">Donde _\<FQDN\>_ es el nombre de dominio completo (FQDN) del servidor de base de datos y _\<instance\>_ es la instancia de base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="70c96-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="70c96-116">Para quitar la base de datos correspondiente al almacén de aplicaciones del grupo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70c96-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="70c96-117">Donde _\<FQDN\>_ es el FQDN del servidor de base de datos y _\<instance\>_ es la instancia de base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="70c96-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="70c96-118">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y, a continuación, entrar si desea detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="70c96-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

