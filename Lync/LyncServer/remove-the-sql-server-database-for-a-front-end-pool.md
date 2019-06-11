---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="a9542-102">Quitar la base de datos de SQL Server para un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a9542-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9542-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a9542-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a9542-104">Después de quitar un grupo front-end de Microsoft Lync Server 2010 o volver a configurar el grupo para que use una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="a9542-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="a9542-105">Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a9542-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="a9542-106">Para quitar la base de datos de SQL Server con el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="a9542-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="a9542-107">Desde el servidor front-end de Lync Server 2013, abra Topology Builder y descargue la topología existente.</span><span class="sxs-lookup"><span data-stu-id="a9542-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="a9542-108">En el generador de topología, vaya a **componentes** compartidos y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al grupo front-end eliminado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a9542-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="a9542-109">Publique la topología y, a continuación, compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="a9542-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="a9542-110">Para quitar bases de datos de usuario y de aplicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9542-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="a9542-111">Para quitar las bases de datos de SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a9542-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="a9542-112">Abrir el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a9542-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="a9542-113">Para quitar la base de datos para el almacén de usuario del grupo, escriba:</span><span class="sxs-lookup"><span data-stu-id="a9542-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="a9542-114">Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de la base de \<datos\> , e instancia es la instancia de la base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="a9542-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="a9542-115">Para quitar la base de datos para el almacén de aplicaciones del grupo, escriba:</span><span class="sxs-lookup"><span data-stu-id="a9542-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="a9542-116">Donde \<FQDN\> es el nombre completo del servidor de la base \<de\> datos e instancia es la instancia de la base de datos nombrada (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="a9542-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="a9542-117">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione **s** (o presione Entrar) para continuar, o presione **N** y después entrar si quiere detener el cmdlet (es decir, en caso de que se produzcan errores).</span><span class="sxs-lookup"><span data-stu-id="a9542-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

