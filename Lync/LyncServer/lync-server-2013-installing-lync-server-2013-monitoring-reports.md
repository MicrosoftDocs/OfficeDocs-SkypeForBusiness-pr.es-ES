---
title: 'Lync Server 2013: instalar los informes de supervisión de Lync Server 2013'
description: 'Lync Server 2013: instalar los informes de supervisión de Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573936"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="dd127-103">Instalación de informes de supervisión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd127-103">Installing Lync Server 2013 Monitoring Reports</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd127-104">_**Última modificación del tema:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="dd127-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="dd127-105">Los informes de supervisión de Microsoft Lync Server 2013 proporcionan una gran cantidad de información sobre la calidad y la cantidad de sesiones de comunicación que tienen vez en la organización.</span><span class="sxs-lookup"><span data-stu-id="dd127-105">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="dd127-106">Sin embargo, los informes de supervisión no se instalan automáticamente al instalar Lync Server 2013; en su lugar, debe instalar los informes de supervisión por separado y solo después de que Lync Server se haya instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dd127-106">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd127-p102">Se recomienda que instale los informes de supervisión en el equipo en el que está instalada la base de datos de supervisión. De este modo, se simplifica el proceso de asignación de permisos para obtener acceso a los informes, ya que si instala los informes de supervisión en el equipo en que se hospeda el almacén de supervisión, no tendrá que configurar los permisos necesarios para que las bases de datos de un equipo interactúen con los servicios de Reporting Services que se ejecutan en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="dd127-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="dd127-109">Los informes de supervisión de Lync Server incluyen más de 30 informes diseñados para proporcionar información detallada sobre las conferencias, las sesiones de mensajería instantánea de punto a punto, los registros de usuario, la aplicación de grupo de respuesta y mucho más.</span><span class="sxs-lookup"><span data-stu-id="dd127-109">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="dd127-110">Para la versión 2013, los informes de supervisión de Lync Server incluyen varias mejoras:</span><span class="sxs-lookup"><span data-stu-id="dd127-110">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="dd127-111">**Informes nuevos sobre la calidad de voz**.</span><span class="sxs-lookup"><span data-stu-id="dd127-111">**New voice quality reports**.</span></span> <span data-ttu-id="dd127-112">Estos nuevos informes incluyen el [Informe de comparación de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), que compara la calidad entre los distintos tipos de llamadas (por ejemplo, entre llamadas cableadas y llamadas inalámbricas); y el [Informe de tiempo de incorporación a la Conferencia en Lync Server 2013](lync-server-2013-conference-join-time-report.md), que proporciona información sobre el tiempo necesario para que los usuarios se unan a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="dd127-112">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="dd127-113">**Informes mejorados para la solución de problemas y el análisis de las sesiones de uso compartido de aplicaciones y de vídeo.**</span><span class="sxs-lookup"><span data-stu-id="dd127-113">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="dd127-114">El [Informe de Resumen de calidad de medios en Lync server 2013](lync-server-2013-media-quality-summary-report.md) proporciona una forma de analizar las llamadas de uso compartido de aplicaciones y vídeo, mientras que el [Informe de rendimiento del servidor de Lync Server 2013](lync-server-2013-server-performance-report.md) detalla el rendimiento de los servidores que generan estas llamadas.</span><span class="sxs-lookup"><span data-stu-id="dd127-114">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="dd127-115">El [Informe de detalles de sesiones punto a punto](lync-server-2013-peer-to-peer-session-detail-report.md) también informa ahora de las métricas de uso compartido de aplicaciones y vídeos en lync Server 2013 y el [Informe de detalles de conferencia en Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="dd127-115">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="dd127-p106">**Rendimiento mejorado de los informes**. Esto incluye una mayor rapidez del tiempo de respuesta y la recuperación de datos, y una navegación por los informes más sencilla y rápida.</span><span class="sxs-lookup"><span data-stu-id="dd127-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="dd127-118">En la documentación sobre los informes de supervisión se puede encontrar más información referente a cada informe individual.</span><span class="sxs-lookup"><span data-stu-id="dd127-118">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd127-119">Hay otro nuevo informe (subinforme detallado de llamadas de QoE) incluido en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd127-119">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="dd127-120">Sin embargo, este informe se utiliza principalmente con fines internos y no está pensado para usarse mediante un acceso directo.</span><span class="sxs-lookup"><span data-stu-id="dd127-120">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="dd127-121">Hay dos formas de instalar los informes de supervisión de Lync Server: puede usar el Asistente para la implementación de Lync Server o puede usar un script de Windows PowerShell incluido en los archivos de instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd127-121">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="dd127-122">Independientemente del método que elija, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="dd127-122">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="dd127-123">Dispone del derecho para agregar un rol de base de datos a una cuenta de usuario de la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="dd127-123">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="dd127-p109">Tiene el rol de administrador de contenido en SQL Server Reporting Services. Este rol le otorga el derecho para implementar informes en SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dd127-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="dd127-126">Para instalar los informes de supervisión con el Asistente para la implementación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dd127-126">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="dd127-127">Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Asistente para la implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dd127-127">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="dd127-128">En el Asistente para la implementación, haga clic en **Implementar los informes de supervisión** para iniciar el asistente de implementación de los informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="dd127-128">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="dd127-p110">Una vez en el asistente, en la página **Especificar la base de datos de supervisión**, asegúrese de que el nombre de dominio completo del equipo en que se hospeda su almacén de supervisión aparece en la lista desplegable **Base de datos de supervisión**. (Si dispone de varios almacenes de supervisión, seleccione el servidor correspondiente en la lista desplegable.) Compruebe que en el cuadro **Instancia de SQL Server Reporting Services (SSRS)** aparece la instancia correcta de SQL Server (por ejemplo, **atl-sql-001.litwareinc.com/archinst**) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dd127-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="dd127-131">En la página **especificar credenciales** , en el cuadro **nombre de usuario** , escriba el nombre de dominio y el nombre de usuario de la cuenta que se va a usar para obtener acceso a los informes de supervisión (por ejemplo, **litwareinc \\ kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="dd127-131">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="dd127-132">Si no usa este formato (nombre de usuario de dominio \\ ), se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="dd127-132">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="dd127-133">Introduzca la contraseña de la cuenta de usuario en el cuadro **Contraseña** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dd127-133">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="dd127-134">Tenga en cuenta que no se requieren derechos especiales para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="dd127-134">Note that no special rights are required for this account.</span></span> <span data-ttu-id="dd127-135">Cuando finalice la instalación, se concederán automáticamente los permisos de base de datos y de inicio de sesión necesarios para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="dd127-135">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="dd127-p113">En la página **Especificar grupo de solo lectura**, en el cuadro Grupo de usuarios, escriba el nombre del grupo de seguridad al que se concederá acceso de solo lectura a SQL Server Reporting Services. Por ejemplo, para conceder acceso de administradores de solo lectura a los informes, escriba **RTCUniversalReadOnlyAdmins**. Después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dd127-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="dd127-139">En la página \*\*Ejecutar comandos \*\*, haga clic en \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="dd127-139">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="dd127-140">Los informes de supervisión también se pueden instalar desde el shell de administración de Lync Server ejecutando el script DeployReports.ps1; Este script de Windows PowerShell se puede encontrar en los medios de instalación de Lync Server en la \\ \\ carpeta SETUP ReportingSetup</span><span class="sxs-lookup"><span data-stu-id="dd127-140">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="dd127-141">Para instalar los informes de supervisión con el script DeployReports.ps1, escriba un comando como el siguiente en el símbolo del sistema del Shell de administración:</span><span class="sxs-lookup"><span data-stu-id="dd127-141">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="dd127-142">En la tabla siguiente se describen los parámetros utilizados en el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="dd127-142">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd127-143">Nombre del parámetro</span><span class="sxs-lookup"><span data-stu-id="dd127-143">Parameter Name</span></span></th>
<th><span data-ttu-id="dd127-144">Necesario</span><span class="sxs-lookup"><span data-stu-id="dd127-144">Required</span></span></th>
<th><span data-ttu-id="dd127-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd127-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd127-146">storedUserName</span><span class="sxs-lookup"><span data-stu-id="dd127-146">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="dd127-147">Sí</span><span class="sxs-lookup"><span data-stu-id="dd127-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd127-148">Cuenta de usuario (en el formato dominio\nombredeusuario) utilizada para obtener acceso al almacén de supervisión; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd127-148">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="dd127-149">La cuenta debe disponer de los permisos indicados anteriormente de SQL Server y SQL Server Reporting Services; si no, el script no funcionará.</span><span class="sxs-lookup"><span data-stu-id="dd127-149">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd127-150">storedPassword</span><span class="sxs-lookup"><span data-stu-id="dd127-150">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="dd127-151">Sí</span><span class="sxs-lookup"><span data-stu-id="dd127-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd127-152">Contraseña para la cuenta de usuario utilizada para obtener acceso al almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="dd127-152">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd127-153">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="dd127-153">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="dd127-154">No</span><span class="sxs-lookup"><span data-stu-id="dd127-154">No</span></span></p></td>
<td><p><span data-ttu-id="dd127-155">Grupo de seguridad local o de dominio a cuyos miembros se les concederá acceso de solo lectura a los informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="dd127-155">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="dd127-156">Tenga en cuenta que el script fallará si el grupo especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="dd127-156">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="dd127-157">Si más tarde decide revocar dichos permisos o si desea conceder permisos de acceso a otros usuarios o grupos, lo podrá hacer con el Administrador de informes de SQL Service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dd127-157">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd127-158">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="dd127-158">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="dd127-159">No</span><span class="sxs-lookup"><span data-stu-id="dd127-159">No</span></span></p></td>
<td><p><span data-ttu-id="dd127-p116">La instancia de SQL Server en que se hospeda el servicio de informes. La instancia se debe especificar usando el nombre de dominio completo del servidor de informes; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd127-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="dd127-162">Si no se incluye el parámetro, el script asumirá que los servicios de informes se hospedan en la misma instancia de SQL Server en la que se hospeda la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="dd127-162">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd127-163">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="dd127-163">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="dd127-164">No</span><span class="sxs-lookup"><span data-stu-id="dd127-164">No</span></span></p></td>
<td><p><span data-ttu-id="dd127-p117">Identidad de servicio para la base de datos de supervisión. Ejecute este comando para obtener las identidades de sus bases de datos de supervisión:</span><span class="sxs-lookup"><span data-stu-id="dd127-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dd127-167">Después de instalar los informes de supervisión, utilice el cmdlet Set-CsReportingConfiguration para configurar la dirección URL usada para el acceso a dichos informes.</span><span class="sxs-lookup"><span data-stu-id="dd127-167">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="dd127-168">Esta tarea se puede llevar a cabo desde el shell de administración de Lync Server; para ello, ejecute el siguiente comando de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd127-168">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="dd127-169">Tenga en cuenta que se recomienda, aunque no es obligatorio, utilizar el protocolo HTTPS en la configuración de la dirección URL de informes:</span><span class="sxs-lookup"><span data-stu-id="dd127-169">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="dd127-p119">En el comando anterior, para la propiedad ReportingUrl debería definirse la dirección URL del Administrador de informes utilizada por SQL Server 2008 R2 Reporting Services. Para determinar la dirección URL del Administrador de informes, siga los pasos siguientes en el equipo en el que se instaló SQL Server Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="dd127-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="dd127-172">Haga clic en Inicio, Todos los programas, Microsoft SQL Server 2008 R2, Herramientas de configuración, y Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dd127-172">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="dd127-p120">En el cuadro de diálogo Conexión de configuración de Reporting Services, asegúrese de que el nombre del equipo de Reporting Services aparece en el cuadro Nombre del servidor. Seleccione la instancia de SQL Server en la lista desplegable de instancias del Servidor de informes y haga clic en Conectar.</span><span class="sxs-lookup"><span data-stu-id="dd127-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="dd127-p121">En el Administrador de configuración de Reporting Services, haga clic en Dirección URL del Administrador de informes. En el panel Dirección URL del Administrador de informes, deberían aparecer una o varias direcciones URL. Puede usar cualquiera de ellas como la dirección URL de informes, aunque, de nuevo, se recomienda que ReportingUrl utilice el protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="dd127-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="dd127-178">Si ha configurado una base de datos reflejada para la base de datos de supervisión, también debe asociar los informes de supervisión con la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="dd127-178">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="dd127-179">Para obtener más información, vea el artículo [asociar informes de supervisión con una base de datos reflejada en Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .</span><span class="sxs-lookup"><span data-stu-id="dd127-179">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

