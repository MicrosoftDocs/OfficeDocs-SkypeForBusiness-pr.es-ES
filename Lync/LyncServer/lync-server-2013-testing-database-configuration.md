---
title: 'Lync Server 2013: probar la configuración de la base de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Prueba de la configuración de bases de datos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de verificación</p></td>
<td><p>Cada día</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins y deben tener privilegios de administrador en SQL Server.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsDatabase</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsDatabase** comprueba la conectividad a una o varias bases de datos de Lync Server 2013. Cuando se ejecuta, el cmdlet **Test-CsDatabase** lee la topología de Lync Server, intenta conectarse a las bases de datos relevantes y, después, informa del éxito o error de cada intento. Si se puede establecer una conexión, el cmdlet también devolverá información como el nombre de la base de datos, la información de la versión de SQL Server y la ubicación de cualquier base de datos reflejada instalada.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el ejemplo 1 comprueba la configuración de la base de datos de administración central.

    Test-CsDatabase -CentralManagementDatabase

El ejemplo 2 verifica todas las bases de datos de Lync Server instaladas en el equipo atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

En el ejemplo 3, la comprobación se realiza solo para la base de datos de archivado instalada en el equipo atl-sql-001.litwareinc.com. Ten en cuenta que el parámetro SqlInstanceName se incluye para especificar la instancia de SQL Server (Archinst) donde se encuentra la base de datos de archivado.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

El comando que se muestra en el ejemplo 4 comprueba las bases de datos instaladas en el equipo local.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la conectividad de la base de datos está configurada correctamente, recibirá un resultado similar a este, con la propiedad Success marcada como **true**:

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

NombreBasededatos: XDS

Orígenes

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Correcta: verdadero

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

NombreBasededatos: Lis

Orígenes

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion :

Correcta: verdadero

Si la base de datos está configurada correctamente pero aún disponible, el campo Success se mostrará como **false**y se proporcionarán más advertencias e información:

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

NombreBasededatos: XDS

Orígenes

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Correcta: falso

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

NombreBasededatos: Lis

Orígenes

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion :

Correcta: falso

ADVERTENCIA: error en la prueba-CsDatabase. Consultar el archivo de registro para obtener un

Análisis detallado y asegurarse de que se solucionan todos los errores (2) y las advertencias (0)

antes de continuar.

ADVERTENCIA: puede encontrar resultados detallados en

"C:\\usuarios\\probando\\AppData\\local\\temporal\\2\\prueba-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsDatabase** podría fallar:

  - Se proporcionó un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Este comando fallará si la base de datos no está configurada correctamente o aún no se ha implementado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

