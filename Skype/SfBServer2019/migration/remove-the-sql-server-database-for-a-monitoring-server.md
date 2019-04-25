---
title: Quitar la base de datos de SQL Server de un servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedan los datos del servidor. Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.
ms.openlocfilehash: 7e299eb2de3fc0820cd4497c2956c71ceec79910
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231374"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="9eea2-104">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="9eea2-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="9eea2-105">Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedan los datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="9eea2-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="9eea2-106">Use los procedimientos siguientes para quitar las definiciones de generador de topología y, a continuación, quitar los archivos de registro y base de datos desde el servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9eea2-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="9eea2-107">Para quitar la base de datos de SQL Server mediante el generador de topología</span><span class="sxs-lookup"><span data-stu-id="9eea2-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="9eea2-108">En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="9eea2-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="9eea2-109">En el generador, vaya a **Componentes compartidos** y, a continuación, en **Almacenes de SQL Server**, haga clic en el servidor SQL Server instancia había asociada con el se ha quitado o volver a configurar el servidor de supervisión y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9eea2-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="9eea2-110">Publique la topología y, a continuación, comprobar el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="9eea2-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="9eea2-111">Para quitar los archivos de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9eea2-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="9eea2-112">Para quitar las bases de datos en el servidor de SQL Server, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor de SQL Server que se van a eliminar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9eea2-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="9eea2-113">Abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="9eea2-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="9eea2-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="9eea2-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="9eea2-115">Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos, y _ \<instancia\> _ , la instancia de base de datos con nombre opcional.</span><span class="sxs-lookup"><span data-stu-id="9eea2-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="9eea2-116">Cuando el cmdlet **Uninstall-CsDataBase** en el que se le pide que confirme acciones, lea la información y, a continuación, presione S (o ENTRAR) para continuar, o presione N y, a continuación, ENTRAR si desea detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="9eea2-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

