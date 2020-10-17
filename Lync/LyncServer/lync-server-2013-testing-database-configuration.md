---
title: 'Lync Server 2013: probar la configuración de la base de datos'
description: 'Lync Server 2013: prueba de la configuración de la base de datos.'
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
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560686"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="e06dc-103">Prueba de la configuración de la base de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e06dc-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e06dc-104">_**Última modificación del tema:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="e06dc-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e06dc-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="e06dc-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e06dc-106">Diario</span><span class="sxs-lookup"><span data-stu-id="e06dc-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e06dc-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="e06dc-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e06dc-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e06dc-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e06dc-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="e06dc-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e06dc-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins y deben tener privilegios de administrador en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e06dc-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="e06dc-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="e06dc-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="e06dc-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e06dc-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e06dc-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e06dc-113">Description</span></span>

<span data-ttu-id="e06dc-114">El cmdlet **Test-CsDatabase** comprueba la conectividad con una o varias bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e06dc-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="e06dc-115">Cuando se ejecuta, el cmdlet **Test-CsDatabase** lee la topología de Lync Server, intenta conectarse a las bases de datos relevantes y, a continuación, devuelve el éxito o error de cada intento.</span><span class="sxs-lookup"><span data-stu-id="e06dc-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="e06dc-116">Si se puede realizar una conexión, el cmdlet también proporcionará información tal como el nombre de la base de datos, versión de SQL Server y la ubicación de las bases de datos reflejadas instaladas.</span><span class="sxs-lookup"><span data-stu-id="e06dc-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e06dc-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="e06dc-117">Running the test</span></span>

<span data-ttu-id="e06dc-118">El comando que se muestra en el ejemplo 1 comprueba la configuración de la base de datos de administración central.</span><span class="sxs-lookup"><span data-stu-id="e06dc-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="e06dc-119">El ejemplo 2 comprueba todas las bases de datos de Lync Server instaladas en el equipo atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e06dc-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="e06dc-p103">En el ejemplo 3, la comprobación se realiza solo para la base de datos de archivado instalada en el equipo atl-sql-001.litwareinc.com. Tenga en cuenta que el parámetro SqlInstanceName se incluye para especificar la instancia de SQL Server (Archinst) donde se encuentra la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="e06dc-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="e06dc-122">El comando que se muestra en el ejemplo 4 comprueba las bases de datos instaladas en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="e06dc-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e06dc-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="e06dc-123">Determining success or failure</span></span>

<span data-ttu-id="e06dc-124">Si la conectividad de base de datos está configurada correctamente, recibirá una salida similar a la siguiente, con la propiedad correcta marcada como **true**:</span><span class="sxs-lookup"><span data-stu-id="e06dc-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="e06dc-125">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e06dc-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e06dc-126">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="e06dc-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e06dc-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e06dc-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e06dc-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e06dc-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e06dc-129">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="e06dc-129">DatabaseName : xds</span></span>

<span data-ttu-id="e06dc-130">DataSource</span><span class="sxs-lookup"><span data-stu-id="e06dc-130">DataSource :</span></span>

<span data-ttu-id="e06dc-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-131">SQLServerVersion :</span></span>

<span data-ttu-id="e06dc-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="e06dc-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="e06dc-133">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-133">InstalledVersion :</span></span>

<span data-ttu-id="e06dc-134">Correcto: true</span><span class="sxs-lookup"><span data-stu-id="e06dc-134">Succeed : True</span></span>

<span data-ttu-id="e06dc-135">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e06dc-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e06dc-136">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="e06dc-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e06dc-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e06dc-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e06dc-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e06dc-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e06dc-139">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="e06dc-139">DatabaseName : lis</span></span>

<span data-ttu-id="e06dc-140">DataSource</span><span class="sxs-lookup"><span data-stu-id="e06dc-140">DataSource :</span></span>

<span data-ttu-id="e06dc-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-141">SQLServerVersion :</span></span>

<span data-ttu-id="e06dc-142">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="e06dc-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="e06dc-143">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-143">InstalledVersion :</span></span>

<span data-ttu-id="e06dc-144">Correcto: true</span><span class="sxs-lookup"><span data-stu-id="e06dc-144">Succeed : True</span></span>

<span data-ttu-id="e06dc-145">Si la base de datos está configurada correctamente pero todavía disponible, el campo correcto se mostrará como **falso**, y se proporcionarán más advertencias e información:</span><span class="sxs-lookup"><span data-stu-id="e06dc-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="e06dc-146">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e06dc-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e06dc-147">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="e06dc-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e06dc-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e06dc-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e06dc-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e06dc-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e06dc-150">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="e06dc-150">DatabaseName : xds</span></span>

<span data-ttu-id="e06dc-151">DataSource</span><span class="sxs-lookup"><span data-stu-id="e06dc-151">DataSource :</span></span>

<span data-ttu-id="e06dc-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-152">SQLServerVersion :</span></span>

<span data-ttu-id="e06dc-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="e06dc-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="e06dc-154">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-154">InstalledVersion :</span></span>

<span data-ttu-id="e06dc-155">Correcto: falso</span><span class="sxs-lookup"><span data-stu-id="e06dc-155">Succeed : False</span></span>

<span data-ttu-id="e06dc-156">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e06dc-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e06dc-157">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="e06dc-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e06dc-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e06dc-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e06dc-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e06dc-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e06dc-160">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="e06dc-160">DatabaseName : lis</span></span>

<span data-ttu-id="e06dc-161">DataSource</span><span class="sxs-lookup"><span data-stu-id="e06dc-161">DataSource :</span></span>

<span data-ttu-id="e06dc-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-162">SQLServerVersion :</span></span>

<span data-ttu-id="e06dc-163">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="e06dc-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="e06dc-164">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e06dc-164">InstalledVersion :</span></span>

<span data-ttu-id="e06dc-165">Correcto: falso</span><span class="sxs-lookup"><span data-stu-id="e06dc-165">Succeed : False</span></span>

<span data-ttu-id="e06dc-166">ADVERTENCIA: Test-CsDatabase detectó errores.</span><span class="sxs-lookup"><span data-stu-id="e06dc-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="e06dc-167">Consulte el archivo de registro para obtener una</span><span class="sxs-lookup"><span data-stu-id="e06dc-167">Consult the log file for a</span></span>

<span data-ttu-id="e06dc-168">Análisis detallado y asegurarse de que se tratan todos los errores (2) y advertencias (0)</span><span class="sxs-lookup"><span data-stu-id="e06dc-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="e06dc-169">antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e06dc-169">before continuing.</span></span>

<span data-ttu-id="e06dc-170">ADVERTENCIA: los resultados detallados se pueden encontrar en</span><span class="sxs-lookup"><span data-stu-id="e06dc-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="e06dc-171">"C: \\ usuarios \\ probando \\ AppData \\ local \\ temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="e06dc-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="e06dc-172">04d593cce8e6.html ".</span><span class="sxs-lookup"><span data-stu-id="e06dc-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e06dc-173">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="e06dc-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="e06dc-174">Estas son algunas de las razones comunes por las que **Test-CsDatabase** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="e06dc-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="e06dc-175">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="e06dc-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e06dc-176">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="e06dc-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e06dc-177">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="e06dc-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e06dc-178">Se producirá un error en este comando si la base de datos está mal configurada o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="e06dc-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e06dc-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e06dc-179">See Also</span></span>


[<span data-ttu-id="e06dc-180">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="e06dc-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="e06dc-181">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="e06dc-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="e06dc-182">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="e06dc-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

