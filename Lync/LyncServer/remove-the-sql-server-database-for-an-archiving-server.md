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
ms.openlocfilehash: d077b21b1b45cc73c268b3dc6294f0a476f48809
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="47425-102">Quitar la base de datos de SQL Server de un servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="47425-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47425-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="47425-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="47425-104">Después de quitar un servidor de archivado de 2010 de Microsoft Lync Server, puede quitar las bases de datos de SQL Server que hospedaban los datos del grupo.</span><span class="sxs-lookup"><span data-stu-id="47425-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="47425-105">Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="47425-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="47425-106">Para quitar la base de datos de SQL Server mediante el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="47425-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="47425-107">En el servidor front-end de Lync Server 2013, abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="47425-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="47425-108">En el generador de topologías, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el servidor de archivado quitado o reconfigurado y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="47425-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="47425-109">Publique la topología y compruebe el estado de replicación.</span><span class="sxs-lookup"><span data-stu-id="47425-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="47425-110">Para quitar los archivos de base de datos del servidor SQL Server</span><span class="sxs-lookup"><span data-stu-id="47425-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="47425-111">Para quitar las bases de datos del servidor SQL Server, debe pertenecer al grupo sysadmin de SQL Server del servidor SQL Server del que se van a eliminar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="47425-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="47425-112">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47425-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="47425-113">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="47425-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="47425-114">Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de base de datos \<e\> instancia es la instancia de base de datos con nombre (es decir, si se definió una).</span><span class="sxs-lookup"><span data-stu-id="47425-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="47425-115">Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y presione **Y** (o Entrar) para continuar, o bien presione **N** y, a continuación, Entrar si desea detener el cmdlet (esto es, cuando haya errores).</span><span class="sxs-lookup"><span data-stu-id="47425-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

