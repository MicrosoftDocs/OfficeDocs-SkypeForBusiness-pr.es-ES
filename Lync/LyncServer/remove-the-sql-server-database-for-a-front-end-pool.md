---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
description: Quite la base de datos de SQL Server de un grupo de servidores front-end.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c5d47e4c52197c5792fa3b7770da7bbd1b26cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551266"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="2ef97-103">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="2ef97-103">Remove the SQL Server database for a Front End pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ef97-104">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2ef97-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2ef97-105">Después de quitar un grupo de servidores front-end de Microsoft Lync Server 2010 o volver a configurar el grupo para que use una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="2ef97-105">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="2ef97-106">Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2ef97-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="2ef97-107">Para quitar la base de datos de SQL Server mediante el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="2ef97-107">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="2ef97-108">Desde el servidor front-end de Lync Server 2013, abra el generador de topologías y descargue la topología existente.</span><span class="sxs-lookup"><span data-stu-id="2ef97-108">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="2ef97-109">En el generador de topologías, vaya a **componentes compartidos** y a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el grupo de servidores front-end quitado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2ef97-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="2ef97-110">Publique la topología y compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="2ef97-110">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="2ef97-111">Para quitar bases de datos de usuarios y aplicaciones del servidor SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ef97-111">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="2ef97-112">Para quitar las bases de datos del servidor SQL Server, debe pertenecer al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2ef97-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="2ef97-113">Abrir Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="2ef97-113">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="2ef97-114">Para quitar la base de datos correspondiente al almacén de usuarios del grupo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ef97-114">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="2ef97-115">Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de base de datos y \<instance\> es la instancia de base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="2ef97-115">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="2ef97-116">Para quitar la base de datos correspondiente al almacén de aplicaciones del grupo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ef97-116">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="2ef97-117">Donde \<FQDN\> es el FQDN del servidor de base de datos y \<instance\> es la instancia de base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="2ef97-117">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="2ef97-118">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y presione **Y** (o Entrar) para continuar, o bien presione **N** y, a continuación, Entrar si desea detener el cmdlet (esto es, cuando haya errores).</span><span class="sxs-lookup"><span data-stu-id="2ef97-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

