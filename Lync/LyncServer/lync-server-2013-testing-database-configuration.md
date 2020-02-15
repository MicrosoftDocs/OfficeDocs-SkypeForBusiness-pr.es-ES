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
ms.openlocfilehash: 45781238f7fb8aa461e050f2e8f0cbf04e45a950
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="be1cc-102">Prueba de la configuración de la base de datos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be1cc-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be1cc-103">_**Última modificación del tema:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="be1cc-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be1cc-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="be1cc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="be1cc-105">Diario</span><span class="sxs-lookup"><span data-stu-id="be1cc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be1cc-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="be1cc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="be1cc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be1cc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be1cc-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="be1cc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="be1cc-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins y deben tener privilegios de administrador en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be1cc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="be1cc-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="be1cc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="be1cc-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be1cc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="be1cc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="be1cc-112">Description</span></span>

<span data-ttu-id="be1cc-113">El cmdlet **Test-CsDatabase** comprueba la conectividad con una o varias bases de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be1cc-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="be1cc-114">Cuando se ejecuta, el cmdlet **Test-CsDatabase** lee la topología de Lync Server, intenta conectarse a las bases de datos relevantes y, a continuación, devuelve el éxito o error de cada intento.</span><span class="sxs-lookup"><span data-stu-id="be1cc-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="be1cc-115">Si se puede realizar una conexión, el cmdlet también proporcionará información tal como el nombre de la base de datos, versión de SQL Server y la ubicación de las bases de datos reflejadas instaladas.</span><span class="sxs-lookup"><span data-stu-id="be1cc-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="be1cc-116">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="be1cc-116">Running the test</span></span>

<span data-ttu-id="be1cc-117">El comando que se muestra en el ejemplo 1 comprueba la configuración de la base de datos de administración central.</span><span class="sxs-lookup"><span data-stu-id="be1cc-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="be1cc-118">El ejemplo 2 comprueba todas las bases de datos de Lync Server instaladas en el equipo atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="be1cc-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="be1cc-p103">En el ejemplo 3, la comprobación se realiza solo para la base de datos de archivado instalada en el equipo atl-sql-001.litwareinc.com. Tenga en cuenta que el parámetro SqlInstanceName se incluye para especificar la instancia de SQL Server (Archinst) donde se encuentra la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="be1cc-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="be1cc-121">El comando que se muestra en el ejemplo 4 comprueba las bases de datos instaladas en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="be1cc-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="be1cc-122">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="be1cc-122">Determining success or failure</span></span>

<span data-ttu-id="be1cc-123">Si la conectividad de base de datos está configurada correctamente, recibirá una salida similar a la siguiente, con la propiedad correcta marcada como **true**:</span><span class="sxs-lookup"><span data-stu-id="be1cc-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="be1cc-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be1cc-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="be1cc-125">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="be1cc-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="be1cc-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="be1cc-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="be1cc-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="be1cc-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="be1cc-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="be1cc-128">DatabaseName : xds</span></span>

<span data-ttu-id="be1cc-129">DataSource</span><span class="sxs-lookup"><span data-stu-id="be1cc-129">DataSource :</span></span>

<span data-ttu-id="be1cc-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-130">SQLServerVersion :</span></span>

<span data-ttu-id="be1cc-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="be1cc-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="be1cc-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-132">InstalledVersion :</span></span>

<span data-ttu-id="be1cc-133">Correcto: true</span><span class="sxs-lookup"><span data-stu-id="be1cc-133">Succeed : True</span></span>

<span data-ttu-id="be1cc-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be1cc-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="be1cc-135">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="be1cc-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="be1cc-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="be1cc-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="be1cc-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="be1cc-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="be1cc-138">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="be1cc-138">DatabaseName : lis</span></span>

<span data-ttu-id="be1cc-139">DataSource</span><span class="sxs-lookup"><span data-stu-id="be1cc-139">DataSource :</span></span>

<span data-ttu-id="be1cc-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-140">SQLServerVersion :</span></span>

<span data-ttu-id="be1cc-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="be1cc-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="be1cc-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-142">InstalledVersion :</span></span>

<span data-ttu-id="be1cc-143">Correcto: true</span><span class="sxs-lookup"><span data-stu-id="be1cc-143">Succeed : True</span></span>

<span data-ttu-id="be1cc-144">Si la base de datos está configurada correctamente pero todavía disponible, el campo correcto se mostrará como **falso**, y se proporcionarán más advertencias e información:</span><span class="sxs-lookup"><span data-stu-id="be1cc-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="be1cc-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be1cc-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="be1cc-146">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="be1cc-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="be1cc-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="be1cc-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="be1cc-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="be1cc-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="be1cc-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="be1cc-149">DatabaseName : xds</span></span>

<span data-ttu-id="be1cc-150">DataSource</span><span class="sxs-lookup"><span data-stu-id="be1cc-150">DataSource :</span></span>

<span data-ttu-id="be1cc-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-151">SQLServerVersion :</span></span>

<span data-ttu-id="be1cc-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="be1cc-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="be1cc-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-153">InstalledVersion :</span></span>

<span data-ttu-id="be1cc-154">Correcto: falso</span><span class="sxs-lookup"><span data-stu-id="be1cc-154">Succeed : False</span></span>

<span data-ttu-id="be1cc-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be1cc-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="be1cc-156">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="be1cc-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="be1cc-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="be1cc-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="be1cc-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="be1cc-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="be1cc-159">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="be1cc-159">DatabaseName : lis</span></span>

<span data-ttu-id="be1cc-160">DataSource</span><span class="sxs-lookup"><span data-stu-id="be1cc-160">DataSource :</span></span>

<span data-ttu-id="be1cc-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-161">SQLServerVersion :</span></span>

<span data-ttu-id="be1cc-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="be1cc-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="be1cc-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="be1cc-163">InstalledVersion :</span></span>

<span data-ttu-id="be1cc-164">Correcto: falso</span><span class="sxs-lookup"><span data-stu-id="be1cc-164">Succeed : False</span></span>

<span data-ttu-id="be1cc-165">ADVERTENCIA: test-CsDatabase detectó errores.</span><span class="sxs-lookup"><span data-stu-id="be1cc-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="be1cc-166">Consulte el archivo de registro para obtener una</span><span class="sxs-lookup"><span data-stu-id="be1cc-166">Consult the log file for a</span></span>

<span data-ttu-id="be1cc-167">Análisis detallado y asegurarse de que se tratan todos los errores (2) y advertencias (0)</span><span class="sxs-lookup"><span data-stu-id="be1cc-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="be1cc-168">antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="be1cc-168">before continuing.</span></span>

<span data-ttu-id="be1cc-169">ADVERTENCIA: los resultados detallados se pueden encontrar en</span><span class="sxs-lookup"><span data-stu-id="be1cc-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="be1cc-170">"C:\\usuarios\\probando\\AppData\\local\\Temp\\2\\test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="be1cc-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="be1cc-171">04d593cce8e6. html ".</span><span class="sxs-lookup"><span data-stu-id="be1cc-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="be1cc-172">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="be1cc-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="be1cc-173">Estas son algunas de las razones comunes por las que **Test-CsDatabase** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="be1cc-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="be1cc-174">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="be1cc-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="be1cc-175">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="be1cc-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="be1cc-176">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="be1cc-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="be1cc-177">Se producirá un error en este comando si la base de datos está mal configurada o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="be1cc-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="be1cc-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="be1cc-178">See Also</span></span>


[<span data-ttu-id="be1cc-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="be1cc-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="be1cc-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="be1cc-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="be1cc-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="be1cc-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

