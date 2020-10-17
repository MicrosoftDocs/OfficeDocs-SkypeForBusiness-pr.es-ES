---
title: 'Lync Server 2013: tareas semanales'
description: 'Lync Server 2013: tareas semanales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d818e1140141a470bb57a1471bb04931f505a6bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546146"
---
# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="b1dd3-103">Tareas semanales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1dd3-103">Weekly tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1dd3-104">_**Última modificación del tema:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="b1dd3-104">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="b1dd3-105">Las tareas semanales suelen estar relacionadas con la recopilación y el análisis de registros e informes.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-105">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="b1dd3-106">Archivar registros de eventos</span><span class="sxs-lookup"><span data-stu-id="b1dd3-106">Archive event logs</span></span>

<span data-ttu-id="b1dd3-107">Si los registros de eventos no se configuran para sobrescribir los eventos según sea necesario, se deben archivar y eliminar con regularidad.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-107">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="b1dd3-108">Esta acción es especialmente importante para los registros de seguridad, lo que puede ser necesario cuando se investiga un intento de infringir la seguridad.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-108">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="b1dd3-109">Su organización tendrá que definir directivas y procedimientos para el archivado de registros.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-109">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="b1dd3-110">Crear informes</span><span class="sxs-lookup"><span data-stu-id="b1dd3-110">Create reports</span></span>

<span data-ttu-id="b1dd3-111">Cree informes de estado para ayudar con la planeación de capacidad, las revisiones de SLA y el análisis de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-111">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="b1dd3-112">Use datos diarios del registro de eventos y el monitor del sistema para crear informes sobre el uso de la CPU, la memoria y el disco.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-112">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="b1dd3-113">Usar System Center Operations Manager para generar informes de disponibilidad y disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-113">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="b1dd3-114">La organización tendrá que definir directivas y procedimientos para los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-114">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="b1dd3-115">Informes de incidentes</span><span class="sxs-lookup"><span data-stu-id="b1dd3-115">Incident reports</span></span>

<span data-ttu-id="b1dd3-116">Realice una auditoría semanal de los informes de incidentes de la organización relacionados con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-116">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="b1dd3-117">Esta auditoría debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-117">This audit should include the following:</span></span>

  - <span data-ttu-id="b1dd3-118">Los principales incidentes generados, resueltos y pendientes.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-118">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="b1dd3-119">Soluciones para incidentes sin resolver.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-119">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="b1dd3-120">Actualizar informes para incluir nuevos vales de problemas.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-120">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="b1dd3-121">Actualización de un repositorio de documentos para las guías de solución de problemas y post mortem sobre las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-121">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="b1dd3-122">Dado que el sistema de seguimiento de incidentes de su organización es una elección independiente de Lync Server, hay instrucciones específicas o punteros que no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-122">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="b1dd3-123">Consulte la documentación del sistema elegido por su organización.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-123">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="b1dd3-124">Comprobar el rendimiento y los registros de IIS</span><span class="sxs-lookup"><span data-stu-id="b1dd3-124">Check IIS logs and performance</span></span>

<span data-ttu-id="b1dd3-125">Realizar una revisión semanal de los registros y el rendimiento de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b1dd3-125">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="b1dd3-126">Para obtener más información acerca de cómo supervisar los registros y el rendimiento de IIS, vea [información general del registro de eventos de Windows Server 2003 Internet Information Services (IIS)](https://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="b1dd3-126">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="b1dd3-127">La revisión debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-127">The review should include the following:</span></span>

  - <span data-ttu-id="b1dd3-128">Contadores de memoria caché de servicio web para supervisar la memoria caché del servicio WWW.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-128">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="b1dd3-129">Contadores de páginas Active Server (ASP) para supervisar las aplicaciones que se ejecutan como ASP.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-129">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="b1dd3-130">Generar informes de base de datos</span><span class="sxs-lookup"><span data-stu-id="b1dd3-130">Generate database reports</span></span>

<span data-ttu-id="b1dd3-131">**Para generar informes en la base de datos SQL**</span><span class="sxs-lookup"><span data-stu-id="b1dd3-131">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="b1dd3-132">Abra Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-132">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="b1dd3-133">En el árbol de la consola, expanda el nodo bosque, expanda grupos de servidores **Enterprise**y, a continuación, haga clic en el grupo de servidores para el que desea generar un informe de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-133">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="b1dd3-134">En el panel de detalles, haga clic en la pestaña **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="b1dd3-134">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="b1dd3-135">En la pestaña **base de datos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-135">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="b1dd3-136">Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-136">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="b1dd3-137">Para recuperar las estadísticas de resumen del usuario actual del grupo de servidores, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-137">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="b1dd3-138">Para recuperar datos por usuario actuales para un solo usuario del grupo de servidores, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-138">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="b1dd3-139">Para recuperar las estadísticas del Resumen de conferencia actual del grupo, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-139">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="b1dd3-140">Buscar actualizaciones de seguridad y Lync Server</span><span class="sxs-lookup"><span data-stu-id="b1dd3-140">Check for security and Lync Server updates</span></span>

<span data-ttu-id="b1dd3-141">Identifique los nuevos Service Packs, revisiones o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-141">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="b1dd3-142">Si es necesario, Pruébelos en un laboratorio de pruebas y use los procedimientos de control de cambios para organizar la implementación en los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-142">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="b1dd3-143">Además, las actualizaciones de componentes de Lync Server ahora están disponibles como parte de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-143">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="b1dd3-144">Todas las actualizaciones de componentes de Lync Server deben actualizarse al mismo tiempo en todos los servidores que ejecutan Lync Server para los que se aplican las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-144">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="b1dd3-145">Ejecutar el analizador de procedimientos recomendados de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1dd3-145">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="b1dd3-146">La herramienta Best Practices Analyzer de Lync Server 2013 es una herramienta de diagnóstico que recopila información de configuración y determina si la configuración se establece de acuerdo con los procedimientos recomendados de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-146">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="b1dd3-147">La documentación de esta herramienta se encuentra en el [analizador de procedimientos recomendados de Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="b1dd3-147">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="b1dd3-148">La herramienta compara los datos de configuración de la implementación con un conjunto de reglas predefinidas para Lync Server y notifica posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-148">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="b1dd3-149">Para cada problema notificado, la herramienta proporciona la configuración actual en el entorno de Lync Server y la configuración recomendada.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-149">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="b1dd3-150">Con el acceso a la red correcto, la herramienta puede examinar su AD DS y los servidores que ejecutan Lync Server 2013 para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-150">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="b1dd3-151">Realizar comprobaciones de estado de forma proactiva, y comprobar que la configuración se establece de acuerdo con los procedimientos recomendados recomendados</span><span class="sxs-lookup"><span data-stu-id="b1dd3-151">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="b1dd3-152">Generar una lista de problemas, como valores de configuración que son subóptimos o opciones no admitidas o no recomendadas</span><span class="sxs-lookup"><span data-stu-id="b1dd3-152">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="b1dd3-153">Juzgar el estado general de un sistema</span><span class="sxs-lookup"><span data-stu-id="b1dd3-153">Judge the general health of a system</span></span>

  - <span data-ttu-id="b1dd3-154">Ayuda para solucionar problemas específicos</span><span class="sxs-lookup"><span data-stu-id="b1dd3-154">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="b1dd3-155">Le pedirá que descargue las actualizaciones si están disponibles</span><span class="sxs-lookup"><span data-stu-id="b1dd3-155">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="b1dd3-156">Proporcionar documentación en línea y local sobre problemas detectados e incluye sugerencias para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="b1dd3-156">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="b1dd3-157">Generar la información de configuración que se puede capturar para una revisión posterior</span><span class="sxs-lookup"><span data-stu-id="b1dd3-157">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="b1dd3-158">Asegúrese de que la RTCBPA.msi esté instalada en todos los servidores de Lync Server 2013 y genere un informe de comprobación del Estado semanal.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-158">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="b1dd3-159">Anote los resultados y corrija si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-159">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="b1dd3-160">Revisión de las cifras de rendimiento del SLA</span><span class="sxs-lookup"><span data-stu-id="b1dd3-160">Review SLA performance figures</span></span>

<span data-ttu-id="b1dd3-161">Compruebe los datos clave de rendimiento de la semana anterior.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-161">Check the key performance data for the previous week.</span></span> <span data-ttu-id="b1dd3-162">Revise el rendimiento con los requisitos del SLA.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-162">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="b1dd3-163">Identificar tendencias y elementos que no han cumplido sus objetivos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-163">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="b1dd3-164">Revisar el paquete de administración de System Center Operations Manager y los informes de calidad de la experiencia</span><span class="sxs-lookup"><span data-stu-id="b1dd3-164">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="b1dd3-165">Obtenga y revise informes del paquete de administración de Lync Server 2013 y de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-165">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="b1dd3-166">Generar y ver informes de base de datos para grupos de servidores Enterprise</span><span class="sxs-lookup"><span data-stu-id="b1dd3-166">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="b1dd3-167">**Para generar informes de grupo**</span><span class="sxs-lookup"><span data-stu-id="b1dd3-167">**To generate pool reports**</span></span>

1.  <span data-ttu-id="b1dd3-168">Abra Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-168">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="b1dd3-169">En el árbol de la consola, expanda el nodo bosque, expanda grupos de servidores **Enterprise**y, a continuación, haga clic en el grupo de servidores para el que desea generar un informe de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-169">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="b1dd3-170">En el panel de detalles, haga clic en la pestaña **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="b1dd3-170">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="b1dd3-171">En la pestaña **base de datos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-171">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="b1dd3-172">Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-172">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="b1dd3-173">Para recuperar las estadísticas de resumen del usuario actual del grupo de servidores, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-173">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="b1dd3-174">Para recuperar datos por usuario actuales para un solo usuario del grupo de servidores, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-174">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="b1dd3-175">Para recuperar las estadísticas del Resumen de conferencia actual del grupo, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-175">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="b1dd3-176">Para cada grupo de servidores Enterprise, los administradores pueden usar la pestaña **base de datos** para ver el nombre de la base de datos y recuperar y ver informes de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-176">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="b1dd3-177">Informes y descripciones de bases de datos</span><span class="sxs-lookup"><span data-stu-id="b1dd3-177">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1dd3-178">Section</span><span class="sxs-lookup"><span data-stu-id="b1dd3-178">Section</span></span></th>
<th><span data-ttu-id="b1dd3-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1dd3-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1dd3-180">Informes de Resumen de usuario</span><span class="sxs-lookup"><span data-stu-id="b1dd3-180">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="b1dd3-181">Dbanalyze/v/Report: diag [/SQLServer: value]</span><span class="sxs-lookup"><span data-stu-id="b1dd3-181">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="b1dd3-182">En esta sección se muestra información agregada sobre los usuarios de un grupo de servidores, como el número de usuarios habilitados, el número medio de contactos por usuario y el número de usuarios para características específicas.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-182">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="b1dd3-183">Al usar estos informes, la siguiente información puede resultar útil:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-183">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="b1dd3-184">Un usuario habilitado es un usuario que está habilitado para Lync Server 2013 mediante el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-184">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="b1dd3-185">Un usuario activo es un usuario que ha iniciado sesión o está registrado.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-185">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="b1dd3-186">Los informes de resumen también ofrecen un conjunto de información estadística sobre los contactos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-186">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="b1dd3-187">Estas estadísticas solo son válidas para el rellenado de los usuarios que han iniciado sesión al menos una vez y que tienen al menos un contacto.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-187">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="b1dd3-188">Por lo tanto, normalmente no verá un número mínimo de contactos de 0.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-188">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="b1dd3-189">Debido a este comportamiento, si un usuario no tiene contactos (pero está activo, en el que el usuario se ha registrado), es posible que vea: &lt; Empty &gt; para algunos campos de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-189">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1dd3-190">Informes de Per-User</span><span class="sxs-lookup"><span data-stu-id="b1dd3-190">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="b1dd3-191">Dbanalyze/v/Report: Disk [/SQLServer: value]</span><span class="sxs-lookup"><span data-stu-id="b1dd3-191">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="b1dd3-192">A diferencia de los informes de Resumen, que se calculan sobre un llenado de usuario, se trata de informes sobre un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-192">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1dd3-193">Informes de Resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="b1dd3-193">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="b1dd3-194">Dbanalyze/v/Report: conf [/SQLServer: valor]</span><span class="sxs-lookup"><span data-stu-id="b1dd3-194">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="b1dd3-195">En esta sección se muestra información agregada sobre estadísticas de Resumen de conferencia para el grupo de servidores, como el número de conferencias activas y el número total de participantes.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-195">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="b1dd3-196">Ejecución del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="b1dd3-196">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b1dd3-197">El analizador de uso de ancho de banda es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por los puntos de conexión de UC a través de vínculos WAN en la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-197">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="b1dd3-198">Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar con la planeación de capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-198">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="b1dd3-199">También recorre en iteración la capacidad de ancho de banda asignada a varios vínculos.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-199">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="b1dd3-200">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-200">This tool does the following:</span></span>

  - <span data-ttu-id="b1dd3-201">Genera informes específicos para el uso de audio a través de la red.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-201">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="b1dd3-202">Ayuda a planear y iterar la capacidad con mayor eficacia en la capacidad de ancho de banda asignada a varios vínculos</span><span class="sxs-lookup"><span data-stu-id="b1dd3-202">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="b1dd3-203">El analizador de uso de ancho de banda puede generar trazados gráficos de capacidad de ancho de banda e informes de uso.</span><span class="sxs-lookup"><span data-stu-id="b1dd3-203">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="b1dd3-204">Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1dd3-204">They are as follows:</span></span>

  - <span data-ttu-id="b1dd3-205">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="b1dd3-205">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="b1dd3-206">Filtrados por los vínculos WAN seleccionados elegidos</span><span class="sxs-lookup"><span data-stu-id="b1dd3-206">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="b1dd3-207">Filtrados por los vínculos WAN que han superado la capacidad de vínculo</span><span class="sxs-lookup"><span data-stu-id="b1dd3-207">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="b1dd3-208">Filtrados por los vínculos WAN que estaban usando el ancho de banda aprovisionado</span><span class="sxs-lookup"><span data-stu-id="b1dd3-208">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="b1dd3-209">Filtra por vínculos WAN que alcanzaban niveles críticos (un uso de ancho de banda superior al 90 por ciento de la capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="b1dd3-209">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="b1dd3-210">Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="b1dd3-210">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="b1dd3-211">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="b1dd3-211">Filtered by network region</span></span>

<span data-ttu-id="b1dd3-212">La documentación de esta herramienta está disponible en la [documentación de las herramientas del kit de recursos de Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="b1dd3-212">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1dd3-213">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1dd3-213">See Also</span></span>


[<span data-ttu-id="b1dd3-214">Lista de comprobación de tareas semanales</span><span class="sxs-lookup"><span data-stu-id="b1dd3-214">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

