---
title: Quitar la base de datos de SQL Server de un servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a820780b7ca3646ba9fa6cc5d02a3c5022db9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="7a16c-102">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="7a16c-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a16c-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7a16c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7a16c-104">Después de quitar un servidor de archivado de Microsoft Lync Server 2010, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="7a16c-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="7a16c-105">Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a16c-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="7a16c-106">Para quitar la base de datos de SQL Server con el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="7a16c-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="7a16c-107">En el servidor front-end de Lync Server 2013, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="7a16c-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="7a16c-108">En el generador de topología, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al servidor de archivado reconfigurado o quitado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7a16c-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="7a16c-109">Publique la topología y, a continuación, compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="7a16c-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="7a16c-110">Para quitar los archivos de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a16c-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="7a16c-111">Para quitar las bases de datos de SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a16c-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="7a16c-112">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a16c-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="7a16c-113">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="7a16c-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="7a16c-114">Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de la base de \<datos\> , e instancia es la instancia de la base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="7a16c-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="7a16c-115">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione **s** (o presione Entrar) para continuar, o presione **N** y después entrar si quiere detener el cmdlet (es decir, en caso de que se produzcan errores).</span><span class="sxs-lookup"><span data-stu-id="7a16c-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

