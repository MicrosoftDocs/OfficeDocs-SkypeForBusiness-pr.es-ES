---
title: Quitar la base de datos de SQL Server de un servidor de supervisión
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
description: Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedaban los datos del servidor. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753332"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="7261a-104">Quitar la base de datos de SQL Server de un servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="7261a-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="7261a-105">Después de quitar un servidor de supervisión, puede quitar las bases de datos de SQL Server que hospedaban los datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="7261a-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="7261a-106">Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7261a-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="7261a-107">Para quitar la base de datos de SQL Server mediante el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="7261a-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="7261a-108">En el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="7261a-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="7261a-109">En el generador de topologías, vaya a **componentes compartidos** y a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el servidor de supervisión quitado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7261a-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="7261a-110">Publique la topología y compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="7261a-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="7261a-111">Para quitar los archivos de base de datos del servidor SQL Server</span><span class="sxs-lookup"><span data-stu-id="7261a-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="7261a-112">Para quitar las bases de datos del servidor basado en SQL Server, el usuario debe ser miembro del grupo sysadmins de SQL Server en el servidor SQL Server del que se vayan a quitar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7261a-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="7261a-113">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7261a-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="7261a-114">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="7261a-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="7261a-115">Donde _\<FQDN\>_ es el nombre de dominio completo (FQDN) del servidor de base de datos y _\<instance\>_ es la instancia opcional de base de datos con nombre.</span><span class="sxs-lookup"><span data-stu-id="7261a-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="7261a-116">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione s (o entrar) para continuar, o presione N y, a continuación, entrar si desea detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="7261a-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

