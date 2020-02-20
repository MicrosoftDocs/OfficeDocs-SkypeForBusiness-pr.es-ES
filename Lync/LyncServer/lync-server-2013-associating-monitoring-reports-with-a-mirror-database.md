---
title: 'Lync Server 2013: Asociación de informes de supervisión con una base de datos reflejada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48dbf5530a071bc1f23f9d2c05d82e151f51f645
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="0f2d5-102">Asociación de informes de supervisión a una base de datos reflejada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f2d5-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f2d5-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0f2d5-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="0f2d5-104">Si configura un reflejo para la base de datos de supervisión, esa base de datos reflejada asumirá el control como la base de datos principal si se produce una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="0f2d5-105">Sin embargo, si usa informes de supervisión de Lync Server y se produce una conmutación por error, es posible que los informes de supervisión no se conecten a la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="0f2d5-106">Esto se debe a que, al instalar los informes de supervisión, solo se especifica la ubicación de la base de datos principal; no se especifica la ubicación de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="0f2d5-107">Para obtener informes de supervisión para la conmutación por error automática en la base de datos reflejada, debe agregar la base de datos reflejada como "asociado de conmutación por error" a las dos bases de datos que usan los informes de supervisión (una base de datos para los datos del registro de detalles de llamadas y la otra para la calidad de Experience (QoE) de datos).</span><span class="sxs-lookup"><span data-stu-id="0f2d5-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="0f2d5-108">(Tenga en cuenta que este paso debe realizarse después de haber instalado los informes de supervisión). Puede Agregar la información del asociado de conmutación por error editando manualmente los valores de la cadena de conexión que usan estas dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="0f2d5-109">Para ello, lleve a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="0f2d5-110">Use Internet Explorer para abrir la Página principal de **SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="0f2d5-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="0f2d5-111">La dirección URL de la Página principal de Reporting Services incluye:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="0f2d5-112">El prefijo **http:** .</span><span class="sxs-lookup"><span data-stu-id="0f2d5-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="0f2d5-113">El nombre de dominio completo (FQDN) del equipo donde está instalado Reporting Services (por ejemplo, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="0f2d5-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="0f2d5-114">La cadena de **caracteres\_/Reports**.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="0f2d5-115">El nombre de la instancia de base de datos donde se instalan los informes de supervisión (por ejemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="0f2d5-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="0f2d5-116">Por ejemplo, si se instaló SQL Server Reporting Services en el equipo atl-sql-001.litwareinc.com y los informes de supervisión usan la instancia de base de datos archinst, la dirección URL de la Página principal tendría el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="0f2d5-117">Una vez que haya tenido acceso a la Página principal de Reporting Services, haga clic en **LyncServerReports**y, a continuación, en **contenido de informes\_**.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="0f2d5-118">Esto le llevará a la página **de\_contenido de informes** de los informes de supervisión de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="0f2d5-119">En la **página\_contenido de informes** , haga clic en el origen de datos **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="0f2d5-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="0f2d5-120">En la página **CDRDB** , en la ficha **propiedades** , busque el cuadro de texto denominado **cadena de conexión**.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="0f2d5-121">La cadena de conexión actual tendrá un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="0f2d5-122">**Origen de datos = (local\\) archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="0f2d5-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="0f2d5-123">Edite la cadena de conexión para incluir el nombre del servidor y la instancia de base de datos de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="0f2d5-124">Por ejemplo, si el servidor se denomina ATL-Mirror-001 y la base de datos reflejada está en la instancia de archinst, tendrá que agregar para especificar la base de datos reflejada con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="0f2d5-125">**Asociado de conmutación por error = ATL-\\Mirror-001 archinst**</span><span class="sxs-lookup"><span data-stu-id="0f2d5-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="0f2d5-126">La cadena de conexión modificada tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="0f2d5-127">**Origen de datos = (local\\) archinst; Asociado de conmutación por error = ATL-\\Mirror-001 archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="0f2d5-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="0f2d5-128">Después de actualizar la cadena de conexión, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="0f2d5-129">En la página **CDRDB** , haga clic en el vínculo **contenido de informes\_** .</span><span class="sxs-lookup"><span data-stu-id="0f2d5-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="0f2d5-130">Haga clic en el origen de datos **QMSDB** y, a continuación, edite la cadena de conexión para la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="0f2d5-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0f2d5-131">For example:</span></span>
    
    <span data-ttu-id="0f2d5-132">**Origen de datos = (local\\) archinst; Asociado de conmutación por error = ATL-\\Mirror-001 archinst; Initial Catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="0f2d5-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="0f2d5-133">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0f2d5-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0f2d5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f2d5-134">See Also</span></span>


[<span data-ttu-id="0f2d5-135">Instalación de informes de supervisión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f2d5-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="0f2d5-136">Uso de informes de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f2d5-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

