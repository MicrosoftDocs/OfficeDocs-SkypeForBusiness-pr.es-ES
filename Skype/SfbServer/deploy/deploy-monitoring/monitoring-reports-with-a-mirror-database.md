---
title: Asociar informes de supervisión con una base de datos reflejada en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumen: obtenga información sobre cómo asociar informes de supervisión con una base de datos reflejada usada por Skype Empresarial Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802170"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="36c56-103">Asociar informes de supervisión con una base de datos reflejada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="36c56-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="36c56-104">**Resumen:** Obtenga información sobre cómo asociar informes de supervisión con una base de datos reflejada usada por Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="36c56-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="36c56-105">Supervisión de informes con una base de datos reflejada</span><span class="sxs-lookup"><span data-stu-id="36c56-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="36c56-106">Si configura un reflejo para la base de datos de supervisión, esa base de datos reflejada tomará el control como base de datos principal si se produce una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="36c56-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="36c56-107">Sin embargo, si usa los informes de supervisión de Skype Empresarial Server y se produce una conmutación por error, es posible que los informes de supervisión no se conecten a la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="36c56-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="36c56-108">Esto se debe a que, al instalar informes de supervisión, solo se especifica la ubicación de la base de datos principal; no se especifica la ubicación de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="36c56-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="36c56-109">Para obtener informes de supervisión para conmutar automáticamente por error a la base de datos reflejada, debe agregar la base de datos reflejada como "socio de conmutación por error" a las dos bases de datos que usan los informes de supervisión (una base de datos para los datos del registro detallado de llamadas y otra para los datos de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="36c56-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="36c56-110">(Tenga en cuenta que este paso debe realizarse después de instalar los informes de supervisión). Puede agregar la información del asociado de conmutación por error editando manualmente los valores de cadena de conexión usados por estas dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="36c56-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="36c56-111">Para ello, lleve a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="36c56-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="36c56-112">Use Internet Explorer para abrir la **página principal SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="36c56-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="36c56-113">La dirección URL de la página principal de Reporting Services incluye:</span><span class="sxs-lookup"><span data-stu-id="36c56-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="36c56-114">Prefijo **http:**</span><span class="sxs-lookup"><span data-stu-id="36c56-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="36c56-115">El nombre de dominio completo (FQDN) del equipo donde está instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="36c56-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="36c56-116">La cadena de caracteres **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="36c56-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="36c56-117">El nombre de la instancia de base de datos donde están instalados los informes de supervisión (por ejemplo, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="36c56-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="36c56-118">Por ejemplo, si SQL Server Reporting Services se instaló en el equipo atl-sql-001.litwareinc.com y los informes de supervisión usan el archivo de instancia de base de datos, la dirección URL de la página principal tendría este aspecto:</span><span class="sxs-lookup"><span data-stu-id="36c56-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="36c56-119">Una vez que haya accedido a la página principal de Reporting Services, haga clic en **ServerReports** y, a **continuación, haga** clic en Reports_Content .</span><span class="sxs-lookup"><span data-stu-id="36c56-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="36c56-120">Esto le llevará a la página **de Reports_Content** para los informes de supervisión de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="36c56-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="36c56-121">En la **Reports_Content** de datos, haga clic en el **origen de datos CDRDB.**</span><span class="sxs-lookup"><span data-stu-id="36c56-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="36c56-122">En la **página CDRDB,** en la pestaña **Propiedades,** busque el cuadro de texto con la etiqueta **Cadena de conexión**.</span><span class="sxs-lookup"><span data-stu-id="36c56-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="36c56-123">La cadena de conexión actual tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="36c56-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="36c56-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="36c56-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="36c56-125">Edite la cadena de conexión para incluir el nombre del servidor y la instancia de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="36c56-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="36c56-126">Por ejemplo, si el servidor se denomina atl-mirror-001 y la base de datos reflejada está en la instancia archinst, deberá agregarla para especificar la base de datos reflejada con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="36c56-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="36c56-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="36c56-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="36c56-128">La cadena de conexión editada tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="36c56-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="36c56-129">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="36c56-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="36c56-130">Después de actualizar la cadena de conexión, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="36c56-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="36c56-131">En la **página CDRDB,** haga clic en **Reports_Content** vínculo.</span><span class="sxs-lookup"><span data-stu-id="36c56-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="36c56-132">Haga clic **en el origen de datos QMSDB** y, a continuación, edite la cadena de conexión de la base de datos QoE.</span><span class="sxs-lookup"><span data-stu-id="36c56-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="36c56-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36c56-133">For example:</span></span>
    
    <span data-ttu-id="36c56-134">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="36c56-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="36c56-135">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="36c56-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="36c56-136">Ver también</span><span class="sxs-lookup"><span data-stu-id="36c56-136">See also</span></span>

[<span data-ttu-id="36c56-137">Instalar informes de supervisión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="36c56-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="36c56-138">Uso de informes de supervisión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="36c56-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
