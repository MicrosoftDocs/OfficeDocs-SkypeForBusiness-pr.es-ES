---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.
ms.openlocfilehash: 8644760f9f3a18f737fcccd80e20eb091efe2f4b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812858"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="72409-104">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="72409-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="72409-105">Después de quitar un grupo de servidores front-end o volver a configurar el grupo para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="72409-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="72409-106">Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="72409-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="72409-107">Para quitar la base de datos de SQL Server con el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="72409-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="72409-108">Desde el servidor front-end de Skype empresarial Server 2019, abra Topology Builder y descargue la topología existente.</span><span class="sxs-lookup"><span data-stu-id="72409-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="72409-109">En el generador de topología, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al grupo front-end eliminado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="72409-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="72409-110">Publique la topología y, a continuación, compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="72409-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="72409-111">Para quitar bases de datos de usuario y de aplicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="72409-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="72409-112">Para quitar las bases de datos de SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="72409-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="72409-113">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="72409-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="72409-114">Para quitar la base de datos para el almacén de usuario del grupo, escriba:</span><span class="sxs-lookup"><span data-stu-id="72409-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="72409-115">Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de la base de datos, e _ \<instancia\> _ es la instancia de la base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="72409-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="72409-116">Para quitar la base de datos para el almacén de aplicaciones del grupo, escriba:</span><span class="sxs-lookup"><span data-stu-id="72409-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="72409-117">Donde _ \<FQDN\> _ es el nombre completo del servidor de la base de datos e _ \<instancia\> _ es la instancia de la base de datos nombrada (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="72409-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="72409-118">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y después entrar si quiere detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="72409-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

