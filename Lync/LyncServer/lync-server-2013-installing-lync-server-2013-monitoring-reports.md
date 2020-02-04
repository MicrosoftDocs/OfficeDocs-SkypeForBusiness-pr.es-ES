---
title: 'Lync Server 2013: instalación de informes de supervisión de Lync Server 2013'
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
ms.openlocfilehash: b6b5f9832ddc10d3cea46d09aee6b047595db0f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="a6c98-102">Instalar los informes de supervisión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6c98-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6c98-103">_**Última modificación del tema:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="a6c98-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="a6c98-104">Los informes de supervisión de Microsoft Lync Server 2013 le proporcionan una gran cantidad de información sobre la calidad y la cantidad de sesiones de comunicación que tienen lugar en su organización.</span><span class="sxs-lookup"><span data-stu-id="a6c98-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="a6c98-105">Sin embargo, los informes de supervisión no se instalan automáticamente al instalar Lync Server 2013; en su lugar, debe instalar los informes de supervisión por separado y solo después de que Lync Server se haya instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a6c98-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6c98-p102">Recomendamos que instale los informes de supervisión en el equipo en el que está instalada la base de datos de supervisión. De este modo, se simplifica el proceso de asignación de permisos para obtener acceso a los informes, ya que si instala los informes de supervisión en el equipo en que se hospeda el almacén de supervisión, no tendrá que configurar los permisos necesarios para que las bases de datos de un equipo interactúen con los servicios de Reporting Services que se ejecutan en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="a6c98-108">Los informes de supervisión de Lync Server incluyen más de 30 informes diseñados para proporcionar información detallada sobre las conferencias, las sesiones de mensajería instantánea de punto a punto, los registros de usuarios, la aplicación de grupo de respuesta y mucho más.</span><span class="sxs-lookup"><span data-stu-id="a6c98-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="a6c98-109">Para la versión de 2013, los informes de supervisión de Lync Server incluyen varias mejoras:</span><span class="sxs-lookup"><span data-stu-id="a6c98-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="a6c98-110">**Informes nuevos sobre la calidad de voz**.</span><span class="sxs-lookup"><span data-stu-id="a6c98-110">**New voice quality reports**.</span></span> <span data-ttu-id="a6c98-111">Estos nuevos informes incluyen el [Informe de comparación de calidad multimedia de Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), que compara la calidad entre los diferentes tipos de llamadas (por ejemplo, entre las llamadas con cable y las llamadas inalámbricas); y el [Informe de tiempo de combinación en conferencia en Lync Server 2013](lync-server-2013-conference-join-time-report.md), que proporciona información acerca de la cantidad de tiempo necesaria para que los usuarios se unan a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a6c98-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="a6c98-112">**Informes mejorados para la solución de problemas y el análisis de las sesiones de uso compartido de aplicaciones y de vídeo.**</span><span class="sxs-lookup"><span data-stu-id="a6c98-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="a6c98-113">El [informe Resumen de calidad de medios de Lync Server 2013](lync-server-2013-media-quality-summary-report.md) ofrece una manera de analizar las llamadas de uso compartido de aplicaciones y vídeo, mientras que el [Informe de rendimiento del servidor de Lync Server 2013](lync-server-2013-server-performance-report.md) detalla el rendimiento de los servidores que generan estas llamadas.</span><span class="sxs-lookup"><span data-stu-id="a6c98-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="a6c98-114">El informe detallado de la sesión de punto a punto también informa de las métricas de uso compartido de aplicaciones y vídeos [en Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) y el [Informe detalles de la Conferencia en Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="a6c98-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="a6c98-p106">**Rendimiento mejorado de los informes**. Esto incluye una mayor rapidez del tiempo de respuesta y la recuperación de datos, y una navegación por los informes más sencilla y rápida.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="a6c98-117">En la documentación sobre los informes de supervisión se puede encontrar más información referente a cada informe individual.</span><span class="sxs-lookup"><span data-stu-id="a6c98-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6c98-118">Hay otro nuevo informe: subinforme de detalles de llamadas de QoE: incluido en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6c98-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="a6c98-119">Pero, este informe se utiliza principalmente con fines internos y no está pensado para usarse por medio de un acceso directo.</span><span class="sxs-lookup"><span data-stu-id="a6c98-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="a6c98-120">Hay dos maneras de instalar los informes de supervisión de Lync Server: puede usar el Asistente para la implementación de Lync Server o puede usar un script de Windows PowerShell incluido con los archivos de instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6c98-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="a6c98-121">Independientemente del método que elija, asegúrese de que:</span><span class="sxs-lookup"><span data-stu-id="a6c98-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="a6c98-122">Dispone del derecho para agregar un rol de base de datos a una cuenta de usuario de la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a6c98-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="a6c98-p109">Tiene el rol de administrador de contenido en SQL Server Reporting Services. Este rol le otorga el derecho para implementar informes en SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="a6c98-125">Para instalar los informes de supervisión con el Asistente para la implementación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a6c98-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="a6c98-126">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a6c98-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="a6c98-127">En el Asistente para la implementación, haga clic en **Implementar los informes de supervisión** para iniciar el asistente de implementación de los informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a6c98-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="a6c98-p110">Una vez en el asistente, en la página **Especificar la base de datos de supervisión**, asegúrese de que el nombre de dominio completo del equipo en que se hospeda su almacén de supervisión aparece en la lista desplegable **Base de datos de supervisión** (si dispone de varios almacenes de supervisión, seleccione el servidor correspondiente en la lista desplegable). Compruebe que en el cuadro **Instancia de SQL Server Reporting Services (SSRS)** aparece la instancia correcta de SQL Server (por ejemplo, **atl-sql-001.litwareinc.com/archinst**) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="a6c98-130">En la página **especificar credenciales** , en el cuadro **nombre de usuario** , escriba el nombre de dominio y el nombre de usuario de la cuenta que se va a usar para acceder a los informes de supervisión (por ejemplo, **litwareinc\\kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="a6c98-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="a6c98-131">Si no usa este formato (nombre de usuario\\de dominio) se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a6c98-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="a6c98-p112">Introduzca la contraseña de la cuenta de usuario en el cuadro **Contraseña** y haga clic en **Siguiente**. Tenga en cuenta que no se requieren permisos especiales para esta cuenta. Cuando termine la instalación, se concederán automáticamente los permisos de base de datos e inicio de sesión requeridos para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p112">Type the user account password in the **Password** box, and then click **Next**. Note that no special rights are required for this account. The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="a6c98-p113">En la página **Especificar grupo de solo lectura**, en el cuadro Grupo de usuarios, escriba el nombre del grupo de seguridad al que se concederá acceso de solo lectura a SQL Server Reporting Services. Por ejemplo, para conceder acceso de administradores de solo lectura a los informes, escriba **RTCUniversalReadOnlyAdmins**. Después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="a6c98-138">En la página **Ejecutar comandos**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a6c98-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="a6c98-139">Los informes de supervisión también se pueden instalar desde el shell de administración de Lync Server ejecutando el script DeployReports. ps1; Este script de Windows PowerShell puede encontrarse en los medios de instalación de \\Lync\\Server, en la carpeta SETUP ReportingSetup</span><span class="sxs-lookup"><span data-stu-id="a6c98-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="a6c98-140">Para instalar los informes de supervisión con DeployReports. ps1, escriba un comando similar al siguiente en el símbolo del sistema de administración:</span><span class="sxs-lookup"><span data-stu-id="a6c98-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="a6c98-141">En la tabla siguiente se describen los parámetros utilizados en el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="a6c98-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6c98-142">Nombre del parámetro</span><span class="sxs-lookup"><span data-stu-id="a6c98-142">Parameter Name</span></span></th>
<th><span data-ttu-id="a6c98-143">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="a6c98-143">Required</span></span></th>
<th><span data-ttu-id="a6c98-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6c98-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6c98-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="a6c98-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="a6c98-146">Sí</span><span class="sxs-lookup"><span data-stu-id="a6c98-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="a6c98-147">Cuenta de usuario (en el formato dominio\nombredeusuario) utilizada para obtener acceso al almacén de supervisión; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6c98-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="a6c98-148">La cuenta necesita disponer de los permisos indicados anteriormente de SQL Server y SQL Server Reporting Services; si no, el script no funcionará.</span><span class="sxs-lookup"><span data-stu-id="a6c98-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6c98-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="a6c98-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="a6c98-150">Sí</span><span class="sxs-lookup"><span data-stu-id="a6c98-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="a6c98-151">Contraseña para la cuenta de usuario utilizada para obtener acceso al almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a6c98-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6c98-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="a6c98-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="a6c98-153">No</span><span class="sxs-lookup"><span data-stu-id="a6c98-153">No</span></span></p></td>
<td><p><span data-ttu-id="a6c98-p115">Grupo de seguridad local o de dominio a cuyos miembros se les concederá acceso de solo lectura a los informes de supervisión. Tenga en cuenta que el script producirá errores si el grupo especificado no existe. Si más tarde decide revocar dichos permisos o si desea conceder permisos de acceso a otros usuarios o grupos, lo podrá hacer con el Administrador de informes de SQL Service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p115">Domain or local security group whose members will be granted read-only access to the Monitoring Reports. Note that the script will fail if the specified group does not exist. If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6c98-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="a6c98-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="a6c98-158">No</span><span class="sxs-lookup"><span data-stu-id="a6c98-158">No</span></span></p></td>
<td><p><span data-ttu-id="a6c98-p116">La instancia de SQL Server en que se hospeda el servicio de informes. La instancia se tiene que especificar usando el nombre de dominio completo del servidor de informes; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6c98-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="a6c98-161">Si no se incluye el parámetro, el script asumirá que los servicios de informes se hospedan en la misma instancia de SQL Server en la que se hospeda la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a6c98-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6c98-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="a6c98-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="a6c98-163">No</span><span class="sxs-lookup"><span data-stu-id="a6c98-163">No</span></span></p></td>
<td><p><span data-ttu-id="a6c98-p117">Identidad de servicio para la base de datos de supervisión. Ejecute este comando para obtener las identidades de sus bases de datos de supervisión:</span><span class="sxs-lookup"><span data-stu-id="a6c98-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a6c98-166">Después de instalar los informes de supervisión, debe usar el cmdlet Set-CsReportingConfiguration para configurar la dirección URL que se usa para acceder a estos informes.</span><span class="sxs-lookup"><span data-stu-id="a6c98-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="a6c98-167">Esta tarea se puede llevar a cabo desde el shell de administración de Lync Server ejecutando el siguiente comando de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6c98-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="a6c98-168">Se recomienda, aunque no es obligatorio, usar el protocolo HTTPS en la configuración de la dirección URL de informes:</span><span class="sxs-lookup"><span data-stu-id="a6c98-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="a6c98-p119">En el comando anterior, para la propiedad ReportingUrl tendría que definirse la dirección URL del Administrador de informes utilizada por SQL Server 2008 R2 Reporting Services. Para determinar la dirección URL del Administrador de informes, siga los pasos siguientes en el equipo en el que se instaló SQL Server Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="a6c98-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="a6c98-171">Haga clic en Inicio, Todos los programas, Microsoft SQL Server 2008 R2, Herramientas de configuración, y Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="a6c98-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="a6c98-p120">En el cuadro de diálogo Conexión de configuración de Reporting Services, asegúrese de que el nombre del equipo de Reporting Services aparece en el cuadro Nombre del servidor. Seleccione la instancia de SQL Server en la lista desplegable de instancias del Servidor de informes y haga clic en Conectar.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="a6c98-p121">En el Administrador de configuración de Reporting Services, haga clic en Dirección URL del Administrador de informes. En el panel Dirección URL del Administrador de informes, tendrían que aparecer una o varias direcciones URL. Puede usar cualquiera de ellas como la dirección URL de informes, aunque, de nuevo, recomendamos que ReportingUrl utilice el protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a6c98-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="a6c98-177">Si ha configurado una base de datos reflejada para la base de datos de supervisión, también tendrá que asociar los informes de supervisión con la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="a6c98-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="a6c98-178">Para obtener más información, vea el artículo [asociar informes de supervisión con una base de datos reflejada en Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .</span><span class="sxs-lookup"><span data-stu-id="a6c98-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

