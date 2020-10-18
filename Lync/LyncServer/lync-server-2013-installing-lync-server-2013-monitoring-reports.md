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
# <a name="installing-lync-server-2013-monitoring-reports"></a>Instalación de informes de supervisión de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-02-27_

Los informes de supervisión de Microsoft Lync Server 2013 proporcionan una gran cantidad de información sobre la calidad y la cantidad de sesiones de comunicación que tienen vez en la organización. Sin embargo, los informes de supervisión no se instalan automáticamente al instalar Lync Server 2013; en su lugar, debe instalar los informes de supervisión por separado y solo después de que Lync Server se haya instalado en el equipo.

<div>


> [!NOTE]  
> Se recomienda que instale los informes de supervisión en el equipo en el que está instalada la base de datos de supervisión. De este modo, se simplifica el proceso de asignación de permisos para obtener acceso a los informes, ya que si instala los informes de supervisión en el equipo en que se hospeda el almacén de supervisión, no tendrá que configurar los permisos necesarios para que las bases de datos de un equipo interactúen con los servicios de Reporting Services que se ejecutan en otro equipo.



</div>

Los informes de supervisión de Lync Server incluyen más de 30 informes diseñados para proporcionar información detallada sobre las conferencias, las sesiones de mensajería instantánea de punto a punto, los registros de usuario, la aplicación de grupo de respuesta y mucho más. Para la versión 2013, los informes de supervisión de Lync Server incluyen varias mejoras:

  - **Informes nuevos sobre la calidad de voz**. Estos nuevos informes incluyen el [Informe de comparación de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), que compara la calidad entre los distintos tipos de llamadas (por ejemplo, entre llamadas cableadas y llamadas inalámbricas); y el [Informe de tiempo de incorporación a la Conferencia en Lync Server 2013](lync-server-2013-conference-join-time-report.md), que proporciona información sobre el tiempo necesario para que los usuarios se unan a una conferencia.

  - **Informes mejorados para la solución de problemas y el análisis de las sesiones de uso compartido de aplicaciones y de vídeo.** El [Informe de Resumen de calidad de medios en Lync server 2013](lync-server-2013-media-quality-summary-report.md) proporciona una forma de analizar las llamadas de uso compartido de aplicaciones y vídeo, mientras que el [Informe de rendimiento del servidor de Lync Server 2013](lync-server-2013-server-performance-report.md) detalla el rendimiento de los servidores que generan estas llamadas. El [Informe de detalles de sesiones punto a punto](lync-server-2013-peer-to-peer-session-detail-report.md) también informa ahora de las métricas de uso compartido de aplicaciones y vídeos en lync Server 2013 y el [Informe de detalles de conferencia en Lync Server 2013](lync-server-2013-conference-detail-report.md).

  - **Rendimiento mejorado de los informes**. Esto incluye una mayor rapidez del tiempo de respuesta y la recuperación de datos, y una navegación por los informes más sencilla y rápida.

En la documentación sobre los informes de supervisión se puede encontrar más información referente a cada informe individual.

<div>


> [!NOTE]  
> Hay otro nuevo informe (subinforme detallado de llamadas de QoE) incluido en Lync Server 2013. Sin embargo, este informe se utiliza principalmente con fines internos y no está pensado para usarse mediante un acceso directo.



</div>

Hay dos formas de instalar los informes de supervisión de Lync Server: puede usar el Asistente para la implementación de Lync Server o puede usar un script de Windows PowerShell incluido en los archivos de instalación de Lync Server 2013. Independientemente del método que elija, asegúrese de que:

  - Dispone del derecho para agregar un rol de base de datos a una cuenta de usuario de la base de datos de supervisión.

  - Tiene el rol de administrador de contenido en SQL Server Reporting Services. Este rol le otorga el derecho para implementar informes en SQL Server Reporting Services.

Para instalar los informes de supervisión con el Asistente para la implementación, siga estos pasos:

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Asistente para la implementación de Lync Server**.

2.  En el Asistente para la implementación, haga clic en **Implementar los informes de supervisión** para iniciar el asistente de implementación de los informes de supervisión.

3.  Una vez en el asistente, en la página **Especificar la base de datos de supervisión**, asegúrese de que el nombre de dominio completo del equipo en que se hospeda su almacén de supervisión aparece en la lista desplegable **Base de datos de supervisión**. (Si dispone de varios almacenes de supervisión, seleccione el servidor correspondiente en la lista desplegable.) Compruebe que en el cuadro **Instancia de SQL Server Reporting Services (SSRS)** aparece la instancia correcta de SQL Server (por ejemplo, **atl-sql-001.litwareinc.com/archinst**) y haga clic en **Siguiente**.

4.  En la página **especificar credenciales** , en el cuadro **nombre de usuario** , escriba el nombre de dominio y el nombre de usuario de la cuenta que se va a usar para obtener acceso a los informes de supervisión (por ejemplo, **litwareinc \\ kenmyer**). Si no usa este formato (nombre de usuario de dominio \\ ), se producirá un error.
    
    Introduzca la contraseña de la cuenta de usuario en el cuadro **Contraseña** y haga clic en **Siguiente**. Tenga en cuenta que no se requieren derechos especiales para esta cuenta. Cuando finalice la instalación, se concederán automáticamente los permisos de base de datos y de inicio de sesión necesarios para la cuenta.

5.  En la página **Especificar grupo de solo lectura**, en el cuadro Grupo de usuarios, escriba el nombre del grupo de seguridad al que se concederá acceso de solo lectura a SQL Server Reporting Services. Por ejemplo, para conceder acceso de administradores de solo lectura a los informes, escriba **RTCUniversalReadOnlyAdmins**. Después, haga clic en **Siguiente**.

6.  En la página **Ejecutar comandos **, haga clic en **Finalizar **.

Los informes de supervisión también se pueden instalar desde el shell de administración de Lync Server ejecutando el script DeployReports.ps1; Este script de Windows PowerShell se puede encontrar en los medios de instalación de Lync Server en la \\ \\ carpeta SETUP ReportingSetup Para instalar los informes de supervisión con el script DeployReports.ps1, escriba un comando como el siguiente en el símbolo del sistema del Shell de administración:

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

En la tabla siguiente se describen los parámetros utilizados en el comando anterior:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre del parámetro</th>
<th>Necesario</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>Sí</p></td>
<td><p>Cuenta de usuario (en el formato dominio\nombredeusuario) utilizada para obtener acceso al almacén de supervisión; por ejemplo:</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>La cuenta debe disponer de los permisos indicados anteriormente de SQL Server y SQL Server Reporting Services; si no, el script no funcionará.</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>Sí</p></td>
<td><p>Contraseña para la cuenta de usuario utilizada para obtener acceso al almacén de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>No</p></td>
<td><p>Grupo de seguridad local o de dominio a cuyos miembros se les concederá acceso de solo lectura a los informes de supervisión. Tenga en cuenta que el script fallará si el grupo especificado no existe. Si más tarde decide revocar dichos permisos o si desea conceder permisos de acceso a otros usuarios o grupos, lo podrá hacer con el Administrador de informes de SQL Service Reporting Services.</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>No</p></td>
<td><p>La instancia de SQL Server en que se hospeda el servicio de informes. La instancia se debe especificar usando el nombre de dominio completo del servidor de informes; por ejemplo:</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>Si no se incluye el parámetro, el script asumirá que los servicios de informes se hospedan en la misma instancia de SQL Server en la que se hospeda la base de datos de supervisión.</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>No</p></td>
<td><p>Identidad de servicio para la base de datos de supervisión. Ejecute este comando para obtener las identidades de sus bases de datos de supervisión:</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


Después de instalar los informes de supervisión, utilice el cmdlet Set-CsReportingConfiguration para configurar la dirección URL usada para el acceso a dichos informes. Esta tarea se puede llevar a cabo desde el shell de administración de Lync Server; para ello, ejecute el siguiente comando de Windows PowerShell. Tenga en cuenta que se recomienda, aunque no es obligatorio, utilizar el protocolo HTTPS en la configuración de la dirección URL de informes:

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

En el comando anterior, para la propiedad ReportingUrl debería definirse la dirección URL del Administrador de informes utilizada por SQL Server 2008 R2 Reporting Services. Para determinar la dirección URL del Administrador de informes, siga los pasos siguientes en el equipo en el que se instaló SQL Server Reporting Services:

1.  Haga clic en Inicio, Todos los programas, Microsoft SQL Server 2008 R2, Herramientas de configuración, y Administrador de configuración de Reporting Services.

2.  En el cuadro de diálogo Conexión de configuración de Reporting Services, asegúrese de que el nombre del equipo de Reporting Services aparece en el cuadro Nombre del servidor. Seleccione la instancia de SQL Server en la lista desplegable de instancias del Servidor de informes y haga clic en Conectar.

3.  En el Administrador de configuración de Reporting Services, haga clic en Dirección URL del Administrador de informes. En el panel Dirección URL del Administrador de informes, deberían aparecer una o varias direcciones URL. Puede usar cualquiera de ellas como la dirección URL de informes, aunque, de nuevo, se recomienda que ReportingUrl utilice el protocolo HTTPS.

Si ha configurado una base de datos reflejada para la base de datos de supervisión, también debe asociar los informes de supervisión con la base de datos reflejada. Para obtener más información, vea el artículo [asociar informes de supervisión con una base de datos reflejada en Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .

</div>

<span> </span>

</div>

</div>

</div>

