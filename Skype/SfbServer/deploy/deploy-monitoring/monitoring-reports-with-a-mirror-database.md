---
title: Asociar informes de supervisión con una base de datos reflejada en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumen: Aprenda a asociar informes de supervisión a una base de datos reflejada usada por Skype empresarial Server.'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273969"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="b2df9-103">Asociar informes de supervisión con una base de datos reflejada en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b2df9-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="b2df9-104">**Resumen:** Obtenga información sobre cómo asociar informes de supervisión a una base de datos reflejada usada por Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b2df9-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="b2df9-105">Supervisar los informes con una base de datos reflejada</span><span class="sxs-lookup"><span data-stu-id="b2df9-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="b2df9-106">Si configura una base de datos reflejada para supervisar su base de datos, la reflejada asumirá el puesto de la base de datos principal cuando se produzca una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b2df9-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="b2df9-107">Sin embargo, si usa los informes de supervisión de Skype empresarial Server y se produce un failover, es posible que los informes de supervisión no se conecten a la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b2df9-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="b2df9-108">Esto se debe a que, al instalar los informes de supervisión, solo se ha especificado la ubicación de la base de datos principal y no la de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b2df9-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="b2df9-p102">Para que los informes de supervisión pasen automáticamente a la base datos reflejada en caso de conmutación por error, necesita agregar la base de datos reflejada como "socio de conmutación por error" a las dos bases de datos que utilizan informes de supervisión (una base datos para los datos del registro detallado de llamadas y otra para los datos de Calidad de la experiencia). Tenga presente que este paso se ha de realizar después de haber instalado los informes de supervisión. Puede agregar información de socio de conmutación por error manualmente editando los valores de la cadena de conexión que utilizan las dos bases de datos. Para ello, realice el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2df9-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="b2df9-p103">Use Internet Explorer para abrir la página de inicio de **SQL Server Reporting Services**. La dirección URL de la página de inicio de Reporting Services está formada por:</span><span class="sxs-lookup"><span data-stu-id="b2df9-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="b2df9-114">El prefijo **http:**.</span><span class="sxs-lookup"><span data-stu-id="b2df9-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="b2df9-115">El nombre de dominio completo (FQDN) del equipo en el que se ha instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="b2df9-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="b2df9-116">La cadena de caracteres **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="b2df9-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="b2df9-117">El nombre de la instancia de la base de datos en la que están instalados los informes de supervisión (por ejemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="b2df9-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="b2df9-118">Por ejemplo, si se ha instalado SQL Server Reporting Services en el equipo atl-sql-001.litwareinc.com y los informes de supervisión utilizan la instancia de base de datos archinst, la dirección URL de la página de inicio será:</span><span class="sxs-lookup"><span data-stu-id="b2df9-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="b2df9-119">Cuando haya obtenido acceso a la página de inicio de Reporting Services, haga clic en **ServerReports** y en **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="b2df9-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="b2df9-120">Esto le llevará a la página **Reports_Content** de los informes de supervisión de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b2df9-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="b2df9-121">En la página **Reports_Content**, haga clic en el origen de datos **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="b2df9-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="b2df9-p105">En la página **CDRDB**, en la ficha **Propiedades**, busque el cuadro de texto titulado **Cadena de conexión**. La cadena de conexión actual será similar a:</span><span class="sxs-lookup"><span data-stu-id="b2df9-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="b2df9-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="b2df9-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="b2df9-p106">Modifique la cadena de conexión para incluir el nombre del servidor y la instancia de base de datos de la base de datos reflejada. Por ejemplo, si el servidor se llama atl-mirror-001 y la base de datos reflejada se encuentra en la instancia archinst, tendrá que agregar para especificar la base de datos reflejada esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b2df9-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="b2df9-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="b2df9-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="b2df9-128">La cadena de conexión resultante necesitará ser:</span><span class="sxs-lookup"><span data-stu-id="b2df9-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="b2df9-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="b2df9-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="b2df9-130">Cuando haya actualizado la cadena de conexión, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b2df9-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="b2df9-p107">En la página **CDRDB**, haga clic en el vínculo **Reports_Content**. Haga clic en el origen de datos **QMSDB** y, luego, modifique la cadena de conexión de la base de datos QoE. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b2df9-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="b2df9-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="b2df9-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="b2df9-135">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b2df9-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b2df9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2df9-136">See also</span></span>

[<span data-ttu-id="b2df9-137">Instalar informes de supervisión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b2df9-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="b2df9-138">Usar informes de supervisión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b2df9-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
