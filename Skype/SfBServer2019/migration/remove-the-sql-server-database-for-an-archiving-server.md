---
title: Quitar la base de datos de SQL Server de un servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231395"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="7ba5e-104">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="7ba5e-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="7ba5e-105">Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedan los datos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="7ba5e-106">Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="7ba5e-107">Para quitar la base de datos de SQL Server mediante el generador de topología</span><span class="sxs-lookup"><span data-stu-id="7ba5e-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="7ba5e-108">En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="7ba5e-109">En el generador, vaya a **Componentes compartidos** y, a continuación, en **Almacenes de SQL Server**, haga clic en el servidor SQL Server instancia había asociada con el se ha quitado o volver a configurar el servidor de archivado y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="7ba5e-110">Publique la topología y, a continuación, comprobar el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="7ba5e-111">Para quitar los archivos de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ba5e-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="7ba5e-112">Para quitar las bases de datos en SQL Server, debe ser miembro del grupo de administradores del sistema de SQL Server para el que se van a eliminar los archivos de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="7ba5e-113">Abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="7ba5e-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="7ba5e-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="7ba5e-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="7ba5e-115">Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos, y _ \<instancia\> _ es la instancia con nombre de la base de datos (es decir, si se ha definido uno).</span><span class="sxs-lookup"><span data-stu-id="7ba5e-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="7ba5e-116">Cuando el cmdlet **Uninstall-CsDataBase** en el que se le pide que confirme acciones, lea la información y, a continuación, presione S (o ENTRAR) para continuar, o presione N y, a continuación, ENTRAR si desea detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="7ba5e-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

