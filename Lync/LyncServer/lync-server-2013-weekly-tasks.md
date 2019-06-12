---
title: 'Lync Server 2013: tareas semanales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="307b0-102">Tareas semanales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="307b0-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="307b0-103">_**Última modificación del tema:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="307b0-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="307b0-104">Las tareas semanales generalmente están relacionadas con la recopilación y el análisis de registros e informes.</span><span class="sxs-lookup"><span data-stu-id="307b0-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="307b0-105">Archivar registros de eventos</span><span class="sxs-lookup"><span data-stu-id="307b0-105">Archive event logs</span></span>

<span data-ttu-id="307b0-106">Si los registros de eventos no están configurados para sobrescribir eventos según sea necesario, se deben archivar y eliminar regularmente.</span><span class="sxs-lookup"><span data-stu-id="307b0-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="307b0-107">Esta acción es especialmente importante para los registros de seguridad, que pueden ser necesarios al investigar intentos de violación de la seguridad.</span><span class="sxs-lookup"><span data-stu-id="307b0-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="307b0-108">Su organización tendrá que definir directivas y procedimientos para el archivado de registro.</span><span class="sxs-lookup"><span data-stu-id="307b0-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="307b0-109">Crear informes</span><span class="sxs-lookup"><span data-stu-id="307b0-109">Create reports</span></span>

<span data-ttu-id="307b0-110">Crear informes de estado para ayudar con el planeamiento de la capacidad, las revisiones de SLA y el análisis de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="307b0-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="307b0-111">Use datos diarios del registro de eventos y el monitor del sistema para crear informes sobre el uso del disco, la memoria y la CPU.</span><span class="sxs-lookup"><span data-stu-id="307b0-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="307b0-112">Use System Center Operations Manager para generar informes de disponibilidad y de tiempo.</span><span class="sxs-lookup"><span data-stu-id="307b0-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="307b0-113">Su organización tendrá que definir directivas y procedimientos para los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="307b0-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="307b0-114">Informes de incidentes</span><span class="sxs-lookup"><span data-stu-id="307b0-114">Incident reports</span></span>

<span data-ttu-id="307b0-115">Realice una auditoría semanal de los informes de incidentes de la organización relacionados con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="307b0-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="307b0-116">Esta auditoría debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="307b0-116">This audit should include the following:</span></span>

  - <span data-ttu-id="307b0-117">Los principales incidentes generados, resueltos y pendientes.</span><span class="sxs-lookup"><span data-stu-id="307b0-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="307b0-118">Soluciones para incidentes sin resolver.</span><span class="sxs-lookup"><span data-stu-id="307b0-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="307b0-119">Actualizar informes para incluir nuevos vales de problemas.</span><span class="sxs-lookup"><span data-stu-id="307b0-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="307b0-120">Actualización de un repositorio de documentos para las guías de solución de problemas y los análisis de las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="307b0-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="307b0-121">Puesto que el sistema de seguimiento de incidentes de su organización es una elección independiente de Lync Server, hay instrucciones específicas o punteros que no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="307b0-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="307b0-122">Consulte la documentación del sistema que eligió su organización.</span><span class="sxs-lookup"><span data-stu-id="307b0-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="307b0-123">Comprobar los registros y el rendimiento de IIS</span><span class="sxs-lookup"><span data-stu-id="307b0-123">Check IIS logs and performance</span></span>

<span data-ttu-id="307b0-124">Realizar una revisión semanal de los registros y el rendimiento de servicios de información de Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="307b0-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="307b0-125">Para obtener más información sobre cómo supervisar los registros y el rendimiento de IIS, vea [información general del registro de eventos de Windows Server 2003 servicios de Internet Information Server (IIS)](http://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="307b0-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="307b0-126">La revisión debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="307b0-126">The review should include the following:</span></span>

  - <span data-ttu-id="307b0-127">Contadores de caché del servicio web para supervisar la caché del servicio WWW.</span><span class="sxs-lookup"><span data-stu-id="307b0-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="307b0-128">Contadores de páginas Active Server (ASP) para supervisar las aplicaciones que se ejecutan como ASP.</span><span class="sxs-lookup"><span data-stu-id="307b0-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="307b0-129">Generar informes de base de datos</span><span class="sxs-lookup"><span data-stu-id="307b0-129">Generate database reports</span></span>

<span data-ttu-id="307b0-130">**Para generar informes en la base de datos SQL**</span><span class="sxs-lookup"><span data-stu-id="307b0-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="307b0-131">Abra Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="307b0-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="307b0-132">En el árbol de consola, expanda el nodo bosque, expanda **grupos empresariales**y, a continuación, haga clic en el grupo para el que desea generar un informe de base de datos.</span><span class="sxs-lookup"><span data-stu-id="307b0-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="307b0-133">En el panel de detalles, haga clic en la pestaña **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="307b0-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="307b0-134">En la pestaña **base de datos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="307b0-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="307b0-135">Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="307b0-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="307b0-136">Para recuperar las estadísticas de Resumen de usuario actuales de la agrupación, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="307b0-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="307b0-137">Para recuperar los datos actuales por usuario para un único usuario del grupo, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="307b0-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="307b0-138">Para recuperar las estadísticas de Resumen de conferencia actuales de la agrupación, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="307b0-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="307b0-139">Comprobar la seguridad y las actualizaciones de Lync Server</span><span class="sxs-lookup"><span data-stu-id="307b0-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="307b0-140">Identifique los nuevos Service Packs, revisiones o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="307b0-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="307b0-141">Si es necesario, Pruébelos en un laboratorio de pruebas y use los procedimientos de control de cambios para organizar la implementación en los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="307b0-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="307b0-142">Además, las actualizaciones de componentes de Lync Server ahora están disponibles como parte de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="307b0-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="307b0-143">Todas las actualizaciones de componentes de Lync Server deben actualizarse al mismo tiempo en todos los servidores que ejecuten Lync Server para los que sean aplicables las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="307b0-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="307b0-144">Ejecutar el analizador de procedimientos recomendados de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="307b0-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="307b0-145">La herramienta Best Practices Analyzer de Lync Server 2013 es una herramienta de diagnóstico que recopila información de configuración y determina si la configuración se establece de acuerdo con las prácticas recomendadas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="307b0-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="307b0-146">La documentación de esta herramienta está en el [analizador de procedimientos recomendados de Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="307b0-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="307b0-147">La herramienta compara los datos de configuración de la implementación con un conjunto de reglas predefinidas para Lync Server e informa de posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="307b0-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="307b0-148">Para cada problema notificado, la herramienta proporciona la configuración actual en el entorno de Lync Server y la configuración recomendada.</span><span class="sxs-lookup"><span data-stu-id="307b0-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="307b0-149">Con el acceso de red correcto, la herramienta puede examinar su AD DS y los servidores que ejecutan Lync Server 2013 para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="307b0-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="307b0-150">Realizar comprobaciones de estado de forma proactiva, comprobando que la configuración se establece de acuerdo con las mejores prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="307b0-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="307b0-151">Generar una lista de problemas, como valores de configuración subóptimos o opciones no compatibles o no recomendadas</span><span class="sxs-lookup"><span data-stu-id="307b0-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="307b0-152">Juzgar el estado general de un sistema</span><span class="sxs-lookup"><span data-stu-id="307b0-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="307b0-153">Ayudar a solucionar problemas específicos</span><span class="sxs-lookup"><span data-stu-id="307b0-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="307b0-154">Le pedirá que descargue las actualizaciones si están disponibles</span><span class="sxs-lookup"><span data-stu-id="307b0-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="307b0-155">Proporcionar documentación en línea y local sobre problemas notificados e incluir sugerencias para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="307b0-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="307b0-156">Generar información de configuración que se puede capturar para una revisión posterior</span><span class="sxs-lookup"><span data-stu-id="307b0-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="307b0-157">Asegúrese de que RTCBPA. msi esté instalado en todos los servidores de Lync Server 2013 y genere un informe de comprobación de Estado semanal.</span><span class="sxs-lookup"><span data-stu-id="307b0-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="307b0-158">Anote los resultados y corríjalos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="307b0-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="307b0-159">Revisar las cifras de rendimiento de SLA</span><span class="sxs-lookup"><span data-stu-id="307b0-159">Review SLA performance figures</span></span>

<span data-ttu-id="307b0-160">Compruebe los datos clave de rendimiento de la semana anterior.</span><span class="sxs-lookup"><span data-stu-id="307b0-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="307b0-161">Revise el rendimiento según los requisitos del SLA.</span><span class="sxs-lookup"><span data-stu-id="307b0-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="307b0-162">Identifique tendencias y elementos que no hayan cumplido sus objetivos.</span><span class="sxs-lookup"><span data-stu-id="307b0-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="307b0-163">Revisar el paquete de administración de System Center Operations Manager y los informes de calidad de experiencia</span><span class="sxs-lookup"><span data-stu-id="307b0-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="307b0-164">Obtener y revisar el paquete de administración de Lync Server 2013 y los informes de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="307b0-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="307b0-165">Generar y ver informes de base de datos para grupos de empresa</span><span class="sxs-lookup"><span data-stu-id="307b0-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="307b0-166">**Para generar informes de grupo**</span><span class="sxs-lookup"><span data-stu-id="307b0-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="307b0-167">Abra Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="307b0-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="307b0-168">En el árbol de consola, expanda el nodo bosque, expanda **grupos empresariales**y, a continuación, haga clic en el grupo para el que desea generar un informe de base de datos.</span><span class="sxs-lookup"><span data-stu-id="307b0-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="307b0-169">En el panel de detalles, haga clic en la pestaña **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="307b0-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="307b0-170">En la pestaña **base de datos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="307b0-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="307b0-171">Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="307b0-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="307b0-172">Para recuperar las estadísticas de Resumen de usuario actuales de la agrupación, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="307b0-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="307b0-173">Para recuperar los datos actuales por usuario para un único usuario del grupo, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="307b0-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="307b0-174">Para recuperar las estadísticas de Resumen de conferencia actuales de la agrupación, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="307b0-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="307b0-175">Para cada grupo de servidores Enterprise, los administradores pueden usar la pestaña **base** de datos para ver el nombre de la base de datos y recuperar y ver informes de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="307b0-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="307b0-176">Informes y descripciones de bases de datos</span><span class="sxs-lookup"><span data-stu-id="307b0-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="307b0-177">Sección</span><span class="sxs-lookup"><span data-stu-id="307b0-177">Section</span></span></th>
<th><span data-ttu-id="307b0-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="307b0-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="307b0-179">Informes de Resumen de usuario</span><span class="sxs-lookup"><span data-stu-id="307b0-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="307b0-180">Dbanalyze/v/Report: diag [/SQLServer: value]</span><span class="sxs-lookup"><span data-stu-id="307b0-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="307b0-181">En esta sección se muestra información de agregado acerca de los usuarios de un grupo, como el número de usuarios habilitados, el número promedio de contactos por usuario y el número de usuarios para características específicas.</span><span class="sxs-lookup"><span data-stu-id="307b0-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="307b0-182">Al usar estos informes, la siguiente información puede resultar útil:</span><span class="sxs-lookup"><span data-stu-id="307b0-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="307b0-183">Un usuario habilitado es un usuario que está habilitado para Lync Server 2013 mediante el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="307b0-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="307b0-184">Un usuario activo es un usuario que ha iniciado sesión o está registrado.</span><span class="sxs-lookup"><span data-stu-id="307b0-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="307b0-185">Los informes de resumen también ofrecen un conjunto de información estadística sobre los contactos.</span><span class="sxs-lookup"><span data-stu-id="307b0-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="307b0-186">Estas estadísticas solo son válidas para la población de usuarios que han iniciado sesión al menos una vez y que tienen al menos un contacto.</span><span class="sxs-lookup"><span data-stu-id="307b0-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="307b0-187">Por lo tanto, generalmente no verás un número mínimo de contactos de 0.</span><span class="sxs-lookup"><span data-stu-id="307b0-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="307b0-188">Debido a este comportamiento, si un usuario no tiene contactos (pero está activo, en el caso de que el usuario haya registrado), es &lt;posible&gt; que vea: vacío para algunos campos de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="307b0-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307b0-189">Informes por usuario</span><span class="sxs-lookup"><span data-stu-id="307b0-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="307b0-190">Dbanalyze/v/Report: Disk [/SQLServer: value]</span><span class="sxs-lookup"><span data-stu-id="307b0-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="307b0-191">A diferencia de los informes de Resumen, que se calculan sobre un llenado de usuario, se trata de informes sobre un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="307b0-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307b0-192">Informes de Resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="307b0-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="307b0-193">Dbanalyze/v/Report: conf [/SQLServer: valor]</span><span class="sxs-lookup"><span data-stu-id="307b0-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="307b0-194">En esta sección se muestra información adicional sobre las estadísticas de Resumen de la Conferencia para el grupo, como el número de conferencias activas y el número total de participantes.</span><span class="sxs-lookup"><span data-stu-id="307b0-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="307b0-195">Ejecución del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="307b0-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="307b0-196">Bandwidth Utilization Analyzer es una herramienta que genera informes sobre diferentes vistas de consumo de ancho de banda por los puntos de conexión de comunicaciones unificadas en vínculos WAN de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="307b0-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="307b0-197">Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar con la planificación de capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="307b0-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="307b0-198">Además, también itera en la capacidad de ancho de banda asignada a diferentes vínculos.</span><span class="sxs-lookup"><span data-stu-id="307b0-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="307b0-199">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="307b0-199">This tool does the following:</span></span>

  - <span data-ttu-id="307b0-200">Genera informes específicos para el uso de audio a través de la red.</span><span class="sxs-lookup"><span data-stu-id="307b0-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="307b0-201">Mejora la eficacia de planificación de capacidad y la iteración en la capacidad de ancho de banda asignada a diferentes vínculos</span><span class="sxs-lookup"><span data-stu-id="307b0-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="307b0-202">El analizador de uso de ancho de banda puede generar trazados gráficos de capacidad de ancho de banda e informes de uso.</span><span class="sxs-lookup"><span data-stu-id="307b0-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="307b0-203">Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="307b0-203">They are as follows:</span></span>

  - <span data-ttu-id="307b0-204">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="307b0-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="307b0-205">Filtrado por los vínculos de WAN seleccionados elegidos</span><span class="sxs-lookup"><span data-stu-id="307b0-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="307b0-206">Filtrados por los vínculos WAN que han superado la capacidad de vínculos</span><span class="sxs-lookup"><span data-stu-id="307b0-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="307b0-207">Filtrado por vínculos WAN que estaban usando el ancho de banda aprovisionado</span><span class="sxs-lookup"><span data-stu-id="307b0-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="307b0-208">Filtrar por vínculos WAN que alcanzaran niveles críticos (un uso de ancho de banda superior al 90 por ciento de la capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="307b0-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="307b0-209">Filtrado por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregional y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="307b0-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="307b0-210">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="307b0-210">Filtered by network region</span></span>

<span data-ttu-id="307b0-211">La documentación de esta herramienta está disponible en la [documentación de las herramientas del kit de recursos de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="307b0-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="307b0-212">Vea también</span><span class="sxs-lookup"><span data-stu-id="307b0-212">See Also</span></span>


[<span data-ttu-id="307b0-213">Lista de comprobación semanal de tareas</span><span class="sxs-lookup"><span data-stu-id="307b0-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

