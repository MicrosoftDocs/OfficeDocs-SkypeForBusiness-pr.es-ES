---
title: Quitar la base de datos de SQL Server de un servidor de archivado
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
description: Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo de servidores. Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753312"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="8d600-104">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="8d600-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="8d600-105">Después de quitar un servidor de archivado, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8d600-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="8d600-106">Use los siguientes procedimientos para quitar las definiciones del Generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="8d600-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="8d600-107">Para quitar la base SQL Server de datos mediante topology Builder</span><span class="sxs-lookup"><span data-stu-id="8d600-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="8d600-108">En el servidor front-end de Skype Empresarial Server 2019, abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="8d600-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="8d600-109">En el Generador de  topologías, vaya a Componentes compartidos y, SQL Server **Almacenes,** haga clic con el botón secundario en la instancia de SQL Server asociada con el servidor de archivado quitado o reconfigurado y, a continuación, haga clic en Eliminar **.**</span><span class="sxs-lookup"><span data-stu-id="8d600-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="8d600-110">Publique la topología y compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="8d600-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="8d600-111">Para quitar los archivos de base de datos del servidor SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d600-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="8d600-112">Para quitar las bases de datos del servidor SQL Server, debe pertenecer al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d600-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="8d600-113">Abra el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8d600-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="8d600-114">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="8d600-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="8d600-115">Donde está el nombre de dominio completo (FQDN) del servidor de base de datos y es la instancia de base de datos con nombre (es decir, si se  _\<FQDN\>_  _\<instance\>_ definió una).</span><span class="sxs-lookup"><span data-stu-id="8d600-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="8d600-116">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione Y (o Entrar) para continuar, o presione N y, a continuación, escriba si desea detener el cmdlet (si hay errores).</span><span class="sxs-lookup"><span data-stu-id="8d600-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

