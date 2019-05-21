---
title: Quitar la base de datos de SQL Server de un servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedaron los datos del servidor. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.
ms.openlocfilehash: 2f4a6feb78adb9daa15cb8d59c2041740e45a19d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301086"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="4fc64-104">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="4fc64-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="4fc64-105">Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedaron los datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="4fc64-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="4fc64-106">Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4fc64-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="4fc64-107">Para quitar la base de datos de SQL Server con el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="4fc64-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="4fc64-108">En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="4fc64-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="4fc64-109">En el generador de topología, vaya a **componentes** compartidos y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al servidor de supervisión eliminado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4fc64-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="4fc64-110">Publique la topología y, a continuación, compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="4fc64-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="4fc64-111">Para quitar los archivos de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4fc64-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="4fc64-112">Para quitar las bases de datos en el servidor basado en SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor de SQL Server en el que va a quitar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4fc64-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="4fc64-113">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4fc64-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="4fc64-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="4fc64-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="4fc64-115">Donde _ \<FQDN\> _ es el nombre de dominio completo (FQDN) del servidor de base de datos _ \<e\> instancia_ es la instancia de base de datos con nombre opcional.</span><span class="sxs-lookup"><span data-stu-id="4fc64-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="4fc64-116">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y después entrar si quiere detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="4fc64-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

