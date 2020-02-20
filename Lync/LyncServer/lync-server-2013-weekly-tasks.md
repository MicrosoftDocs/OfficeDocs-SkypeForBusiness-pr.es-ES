---
title: 'Lync Server 2013: tareas semanales'
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
ms.openlocfilehash: da6e0eb7c4377941992dfba9dd11312a12ee29a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="117eb-102">Tareas semanales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="117eb-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="117eb-103">_**Última modificación del tema:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="117eb-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="117eb-104">Las tareas semanales suelen estar relacionadas con la recopilación y el análisis de registros e informes.</span><span class="sxs-lookup"><span data-stu-id="117eb-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="117eb-105">Archivar registros de eventos</span><span class="sxs-lookup"><span data-stu-id="117eb-105">Archive event logs</span></span>

<span data-ttu-id="117eb-106">Si los registros de eventos no se configuran para sobrescribir los eventos según sea necesario, se deben archivar y eliminar con regularidad.</span><span class="sxs-lookup"><span data-stu-id="117eb-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="117eb-107">Esta acción es especialmente importante para los registros de seguridad, lo que puede ser necesario cuando se investiga un intento de infringir la seguridad.</span><span class="sxs-lookup"><span data-stu-id="117eb-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="117eb-108">Su organización tendrá que definir directivas y procedimientos para el archivado de registros.</span><span class="sxs-lookup"><span data-stu-id="117eb-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="117eb-109">Crear informes</span><span class="sxs-lookup"><span data-stu-id="117eb-109">Create reports</span></span>

<span data-ttu-id="117eb-110">Cree informes de estado para ayudar con la planeación de capacidad, las revisiones de SLA y el análisis de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="117eb-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="117eb-111">Use datos diarios del registro de eventos y el monitor del sistema para crear informes sobre el uso de la CPU, la memoria y el disco.</span><span class="sxs-lookup"><span data-stu-id="117eb-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="117eb-112">Usar System Center Operations Manager para generar informes de disponibilidad y disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="117eb-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="117eb-113">La organización tendrá que definir directivas y procedimientos para los informes de estado.</span><span class="sxs-lookup"><span data-stu-id="117eb-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="117eb-114">Informes de incidentes</span><span class="sxs-lookup"><span data-stu-id="117eb-114">Incident reports</span></span>

<span data-ttu-id="117eb-115">Realice una auditoría semanal de los informes de incidentes de la organización relacionados con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="117eb-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="117eb-116">Esta auditoría debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="117eb-116">This audit should include the following:</span></span>

  - <span data-ttu-id="117eb-117">Los principales incidentes generados, resueltos y pendientes.</span><span class="sxs-lookup"><span data-stu-id="117eb-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="117eb-118">Soluciones para incidentes sin resolver.</span><span class="sxs-lookup"><span data-stu-id="117eb-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="117eb-119">Actualizar informes para incluir nuevos vales de problemas.</span><span class="sxs-lookup"><span data-stu-id="117eb-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="117eb-120">Actualización de un repositorio de documentos para las guías de solución de problemas y post mortem sobre las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="117eb-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="117eb-121">Dado que el sistema de seguimiento de incidentes de su organización es una elección independiente de Lync Server, hay instrucciones específicas o punteros que no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="117eb-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="117eb-122">Consulte la documentación del sistema elegido por su organización.</span><span class="sxs-lookup"><span data-stu-id="117eb-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="117eb-123">Comprobar el rendimiento y los registros de IIS</span><span class="sxs-lookup"><span data-stu-id="117eb-123">Check IIS logs and performance</span></span>

<span data-ttu-id="117eb-124">Realizar una revisión semanal de los registros y el rendimiento de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="117eb-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="117eb-125">Para obtener más información acerca de cómo supervisar los registros y el rendimiento de IIS, vea [información general del registro de eventos de Windows Server 2003 Internet Information Services (IIS)](https://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="117eb-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="117eb-126">La revisión debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="117eb-126">The review should include the following:</span></span>

  - <span data-ttu-id="117eb-127">Contadores de memoria caché de servicio web para supervisar la memoria caché del servicio WWW.</span><span class="sxs-lookup"><span data-stu-id="117eb-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="117eb-128">Contadores de páginas Active Server (ASP) para supervisar las aplicaciones que se ejecutan como ASP.</span><span class="sxs-lookup"><span data-stu-id="117eb-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="117eb-129">Generar informes de base de datos</span><span class="sxs-lookup"><span data-stu-id="117eb-129">Generate database reports</span></span>

<span data-ttu-id="117eb-130">**Para generar informes en la base de datos SQL**</span><span class="sxs-lookup"><span data-stu-id="117eb-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="117eb-131">Abra Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="117eb-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="117eb-132">En el árbol de la consola, expanda el nodo bosque, expanda grupos de servidores **Enterprise**y, a continuación, haga clic en el grupo de servidores para el que desea generar un informe de base de datos.</span><span class="sxs-lookup"><span data-stu-id="117eb-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="117eb-133">En el panel de detalles, haga clic en la pestaña **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="117eb-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="117eb-134">En la pestaña **base de datos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="117eb-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="117eb-135">Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="117eb-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="117eb-136">Para recuperar las estadísticas de resumen del usuario actual del grupo de servidores, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="117eb-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="117eb-137">Para recuperar datos por usuario actuales para un solo usuario del grupo de servidores, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="117eb-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="117eb-138">Para recuperar las estadísticas del Resumen de conferencia actual del grupo, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="117eb-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="117eb-139">Buscar actualizaciones de seguridad y Lync Server</span><span class="sxs-lookup"><span data-stu-id="117eb-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="117eb-140">Identifique los nuevos Service Packs, revisiones o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="117eb-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="117eb-141">Si es necesario, Pruébelos en un laboratorio de pruebas y use los procedimientos de control de cambios para organizar la implementación en los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="117eb-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="117eb-142">Además, las actualizaciones de componentes de Lync Server ahora están disponibles como parte de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="117eb-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="117eb-143">Todas las actualizaciones de componentes de Lync Server deben actualizarse al mismo tiempo en todos los servidores que ejecutan Lync Server para los que se aplican las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="117eb-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="117eb-144">Ejecutar el analizador de procedimientos recomendados de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="117eb-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="117eb-145">La herramienta Best Practices Analyzer de Lync Server 2013 es una herramienta de diagnóstico que recopila información de configuración y determina si la configuración se establece de acuerdo con los procedimientos recomendados de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="117eb-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="117eb-146">La documentación de esta herramienta se encuentra en el [analizador de procedimientos recomendados de Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="117eb-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="117eb-147">La herramienta compara los datos de configuración de la implementación con un conjunto de reglas predefinidas para Lync Server y notifica posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="117eb-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="117eb-148">Para cada problema notificado, la herramienta proporciona la configuración actual en el entorno de Lync Server y la configuración recomendada.</span><span class="sxs-lookup"><span data-stu-id="117eb-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="117eb-149">Con el acceso a la red correcto, la herramienta puede examinar su AD DS y los servidores que ejecutan Lync Server 2013 para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="117eb-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="117eb-150">Realizar comprobaciones de estado de forma proactiva, y comprobar que la configuración se establece de acuerdo con los procedimientos recomendados recomendados</span><span class="sxs-lookup"><span data-stu-id="117eb-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="117eb-151">Generar una lista de problemas, como valores de configuración que son subóptimos o opciones no admitidas o no recomendadas</span><span class="sxs-lookup"><span data-stu-id="117eb-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="117eb-152">Juzgar el estado general de un sistema</span><span class="sxs-lookup"><span data-stu-id="117eb-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="117eb-153">Ayuda para solucionar problemas específicos</span><span class="sxs-lookup"><span data-stu-id="117eb-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="117eb-154">Le pedirá que descargue las actualizaciones si están disponibles</span><span class="sxs-lookup"><span data-stu-id="117eb-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="117eb-155">Proporcionar documentación en línea y local sobre problemas detectados e incluye sugerencias para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="117eb-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="117eb-156">Generar la información de configuración que se puede capturar para una revisión posterior</span><span class="sxs-lookup"><span data-stu-id="117eb-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="117eb-157">Asegúrese de que RTCBPA. msi está instalado en todos los servidores de Lync Server 2013 y genere un informe de comprobación del Estado semanal.</span><span class="sxs-lookup"><span data-stu-id="117eb-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="117eb-158">Anote los resultados y corrija si es necesario.</span><span class="sxs-lookup"><span data-stu-id="117eb-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="117eb-159">Revisión de las cifras de rendimiento del SLA</span><span class="sxs-lookup"><span data-stu-id="117eb-159">Review SLA performance figures</span></span>

<span data-ttu-id="117eb-160">Compruebe los datos clave de rendimiento de la semana anterior.</span><span class="sxs-lookup"><span data-stu-id="117eb-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="117eb-161">Revise el rendimiento con los requisitos del SLA.</span><span class="sxs-lookup"><span data-stu-id="117eb-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="117eb-162">Identificar tendencias y elementos que no han cumplido sus objetivos.</span><span class="sxs-lookup"><span data-stu-id="117eb-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="117eb-163">Revisar el paquete de administración de System Center Operations Manager y los informes de calidad de la experiencia</span><span class="sxs-lookup"><span data-stu-id="117eb-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="117eb-164">Obtenga y revise informes del paquete de administración de Lync Server 2013 y de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="117eb-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="117eb-165">Generar y ver informes de base de datos para grupos de servidores Enterprise</span><span class="sxs-lookup"><span data-stu-id="117eb-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="117eb-166">**Para generar informes de grupo**</span><span class="sxs-lookup"><span data-stu-id="117eb-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="117eb-167">Abra Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="117eb-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="117eb-168">En el árbol de la consola, expanda el nodo bosque, expanda grupos de servidores **Enterprise**y, a continuación, haga clic en el grupo de servidores para el que desea generar un informe de base de datos.</span><span class="sxs-lookup"><span data-stu-id="117eb-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="117eb-169">En el panel de detalles, haga clic en la pestaña **base de datos** .</span><span class="sxs-lookup"><span data-stu-id="117eb-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="117eb-170">En la pestaña **base de datos** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="117eb-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="117eb-171">Para ver el nombre de la base de datos, expanda **Configuración general**y vea el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="117eb-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="117eb-172">Para recuperar las estadísticas de resumen del usuario actual del grupo de servidores, expanda **informes de Resumen de usuario**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="117eb-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="117eb-173">Para recuperar datos por usuario actuales para un solo usuario del grupo de servidores, expanda **informes por usuario**, escriba el URI del SIP del usuario, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="117eb-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="117eb-174">Para recuperar las estadísticas del Resumen de conferencia actual del grupo, expanda **informes de Resumen de conferencia**, haga clic en **ir**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="117eb-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="117eb-175">Para cada grupo de servidores Enterprise, los administradores pueden usar la pestaña **base de datos** para ver el nombre de la base de datos y recuperar y ver informes de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="117eb-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="117eb-176">Informes y descripciones de bases de datos</span><span class="sxs-lookup"><span data-stu-id="117eb-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="117eb-177">Section</span><span class="sxs-lookup"><span data-stu-id="117eb-177">Section</span></span></th>
<th><span data-ttu-id="117eb-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="117eb-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="117eb-179">Informes de Resumen de usuario</span><span class="sxs-lookup"><span data-stu-id="117eb-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="117eb-180">Dbanalyze/v/Report: diag [/SQLServer: value]</span><span class="sxs-lookup"><span data-stu-id="117eb-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="117eb-181">En esta sección se muestra información agregada sobre los usuarios de un grupo de servidores, como el número de usuarios habilitados, el número medio de contactos por usuario y el número de usuarios para características específicas.</span><span class="sxs-lookup"><span data-stu-id="117eb-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="117eb-182">Al usar estos informes, la siguiente información puede resultar útil:</span><span class="sxs-lookup"><span data-stu-id="117eb-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="117eb-183">Un usuario habilitado es un usuario que está habilitado para Lync Server 2013 mediante el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="117eb-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="117eb-184">Un usuario activo es un usuario que ha iniciado sesión o está registrado.</span><span class="sxs-lookup"><span data-stu-id="117eb-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="117eb-185">Los informes de resumen también ofrecen un conjunto de información estadística sobre los contactos.</span><span class="sxs-lookup"><span data-stu-id="117eb-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="117eb-186">Estas estadísticas solo son válidas para el rellenado de los usuarios que han iniciado sesión al menos una vez y que tienen al menos un contacto.</span><span class="sxs-lookup"><span data-stu-id="117eb-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="117eb-187">Por lo tanto, normalmente no verá un número mínimo de contactos de 0.</span><span class="sxs-lookup"><span data-stu-id="117eb-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="117eb-188">Debido a este comportamiento, si un usuario no tiene contactos (pero está activo, en el que el usuario se ha registrado), es posible &lt;que&gt; vea: Empty para algunos campos de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="117eb-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="117eb-189">Informes por usuario</span><span class="sxs-lookup"><span data-stu-id="117eb-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="117eb-190">Dbanalyze/v/Report: Disk [/SQLServer: value]</span><span class="sxs-lookup"><span data-stu-id="117eb-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="117eb-191">A diferencia de los informes de Resumen, que se calculan sobre un llenado de usuario, se trata de informes sobre un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="117eb-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="117eb-192">Informes de Resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="117eb-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="117eb-193">Dbanalyze/v/Report: conf [/SQLServer: valor]</span><span class="sxs-lookup"><span data-stu-id="117eb-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="117eb-194">En esta sección se muestra información agregada sobre estadísticas de Resumen de conferencia para el grupo de servidores, como el número de conferencias activas y el número total de participantes.</span><span class="sxs-lookup"><span data-stu-id="117eb-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="117eb-195">Ejecución del analizador de uso de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="117eb-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="117eb-196">El analizador de uso de ancho de banda es una herramienta que crea informes sobre diversas vistas de consumo de ancho de banda por los puntos de conexión de UC a través de vínculos WAN en la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="117eb-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="117eb-197">Estos informes se pueden usar para comprender el patrón de consumo de ancho de banda actual y para ayudar con la planeación de capacidad de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="117eb-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="117eb-198">También recorre en iteración la capacidad de ancho de banda asignada a varios vínculos.</span><span class="sxs-lookup"><span data-stu-id="117eb-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="117eb-199">Esta herramienta hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="117eb-199">This tool does the following:</span></span>

  - <span data-ttu-id="117eb-200">Genera informes específicos para el uso de audio a través de la red.</span><span class="sxs-lookup"><span data-stu-id="117eb-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="117eb-201">Ayuda a planear y iterar la capacidad con mayor eficacia en la capacidad de ancho de banda asignada a varios vínculos</span><span class="sxs-lookup"><span data-stu-id="117eb-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="117eb-202">El analizador de uso de ancho de banda puede generar trazados gráficos de capacidad de ancho de banda e informes de uso.</span><span class="sxs-lookup"><span data-stu-id="117eb-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="117eb-203">Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="117eb-203">They are as follows:</span></span>

  - <span data-ttu-id="117eb-204">Todos los vínculos WAN en la red empresarial</span><span class="sxs-lookup"><span data-stu-id="117eb-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="117eb-205">Filtrados por los vínculos WAN seleccionados elegidos</span><span class="sxs-lookup"><span data-stu-id="117eb-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="117eb-206">Filtrados por los vínculos WAN que han superado la capacidad de vínculo</span><span class="sxs-lookup"><span data-stu-id="117eb-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="117eb-207">Filtrados por los vínculos WAN que estaban usando el ancho de banda aprovisionado</span><span class="sxs-lookup"><span data-stu-id="117eb-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="117eb-208">Filtra por vínculos WAN que alcanzaban niveles críticos (un uso de ancho de banda superior al 90 por ciento de la capacidad de ancho de banda del vínculo WAN)</span><span class="sxs-lookup"><span data-stu-id="117eb-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="117eb-209">Filtrados por tipo de vínculo WAN: vínculos de sitios de red, vínculos interregionales y vínculos dentro de un sitio</span><span class="sxs-lookup"><span data-stu-id="117eb-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="117eb-210">Filtrados por región de red</span><span class="sxs-lookup"><span data-stu-id="117eb-210">Filtered by network region</span></span>

<span data-ttu-id="117eb-211">La documentación de esta herramienta está disponible en la [documentación de las herramientas del kit de recursos de Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="117eb-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="117eb-212">Vea también</span><span class="sxs-lookup"><span data-stu-id="117eb-212">See Also</span></span>


[<span data-ttu-id="117eb-213">Lista de comprobación de tareas semanales</span><span class="sxs-lookup"><span data-stu-id="117eb-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

