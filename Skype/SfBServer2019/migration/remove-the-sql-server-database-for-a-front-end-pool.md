---
title: Quitar la base de datos de SQL Server para un grupo de servidores Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de quitar un grupo de servidores Front-End o volver a configurar el grupo de servidores para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
ms.openlocfilehash: 35c9429fc16aef886945f8b0adcd5894ce40b834
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373129"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="c8a8e-104">Quitar la base de datos de SQL Server para un grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="c8a8e-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="c8a8e-105">Después de quitar un grupo de servidores Front-End o volver a configurar el grupo de servidores para usar una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="c8a8e-106">Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c8a8e-107">Para quitar la base de datos de SQL Server mediante el generador de topología</span><span class="sxs-lookup"><span data-stu-id="c8a8e-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="c8a8e-108">De Skype para profesionales de 2019 Front-End Server, abra el generador de topologías y descargue la topología existente.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="c8a8e-109">En el generador, vaya a **Componentes compartidos** y, a continuación, en **Almacenes de SQL Server**, haga clic en la instancia de SQL Server asociada con el grupo de servidores Front-End se ha quitado o reconfigurado y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="c8a8e-110">Publique la topología y, a continuación, compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="c8a8e-111">Para quitar las bases de datos de usuario y la aplicación de SQL server</span><span class="sxs-lookup"><span data-stu-id="c8a8e-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="c8a8e-112">Para quitar las bases de datos en SQL server, debe ser miembro del grupo de administradores del sistema de SQL Server para el que se van a eliminar los archivos de base de datos SQL server.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="c8a8e-113">Abra Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="c8a8e-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="c8a8e-114">Para quitar la base de datos para el almacén de usuario del grupo, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8a8e-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c8a8e-115">Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos, y _ \<instancia\> _ es la instancia con nombre de la base de datos (es decir, si se ha definido uno).</span><span class="sxs-lookup"><span data-stu-id="c8a8e-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="c8a8e-116">Para quitar la base de datos para el almacén de aplicación de grupo de servidores, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8a8e-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c8a8e-117">Donde _ \<FQDN\> _ es el FQDN del servidor de base de datos, y _ \<instancia\> _ es la instancia con nombre de la base de datos (es decir, si se ha definido uno).</span><span class="sxs-lookup"><span data-stu-id="c8a8e-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="c8a8e-118">Cuando el cmdlet **Uninstall-CsDataBase** en el que se le pide que confirme acciones, lea la información y, a continuación, presione S (o ENTRAR) para continuar, o presione N y, a continuación, ENTRAR si desea detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="c8a8e-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

