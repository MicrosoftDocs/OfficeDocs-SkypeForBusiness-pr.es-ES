---
title: 'Lync Server 2013: probar el servicio de réplicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="a00cf-102">Probar el servicio de réplicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a00cf-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a00cf-103">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a00cf-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a00cf-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="a00cf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a00cf-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="a00cf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00cf-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="a00cf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a00cf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a00cf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00cf-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="a00cf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a00cf-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a00cf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a00cf-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="a00cf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="a00cf-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a00cf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a00cf-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a00cf-112">Description</span></span>

<span data-ttu-id="a00cf-113">El cmdlet **Test-CsReplica** verifica que el servicio de réplica de Lync Server 2013 se esté ejecutando en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a00cf-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="a00cf-114">El cmdlet **Test-CsReplica** realiza estas tareas como:</span><span class="sxs-lookup"><span data-stu-id="a00cf-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="a00cf-115">comprobar el estado del agente de replicación y los servicios de agente de registro centralizados</span><span class="sxs-lookup"><span data-stu-id="a00cf-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="a00cf-116">comprobando que los puertos necesarios se abrieron en el Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="a00cf-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="a00cf-117">asegurándose de que existen los grupos de seguridad de Active Directory y de equipo local necesarios.</span><span class="sxs-lookup"><span data-stu-id="a00cf-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="a00cf-118">Ten en cuenta que este cmdlet debe ejecutarse de forma local.</span><span class="sxs-lookup"><span data-stu-id="a00cf-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="a00cf-119">Es decir, debe ejecutarse en el mismo equipo en el que se ejecuta el servicio de réplicas.</span><span class="sxs-lookup"><span data-stu-id="a00cf-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="a00cf-120">No hay opciones para ejecutar el cmdlet **Test-CsReplica** en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="a00cf-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a00cf-121">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="a00cf-121">Running the test</span></span>

<span data-ttu-id="a00cf-122">El comando que se muestra en el ejemplo 1 prueba el servicio de réplica de 2013 de Lync Server en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a00cf-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="a00cf-123">En este ejemplo, el parámetro verbose se usa para garantizar que se muestra en pantalla la información sobre la prueba, incluido el error eventual o el éxito de la prueba y la ubicación del informe generado por la prueba.</span><span class="sxs-lookup"><span data-stu-id="a00cf-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="a00cf-124">El ejemplo 2 es una variación del comando que se muestra en el ejemplo 1.</span><span class="sxs-lookup"><span data-stu-id="a00cf-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="a00cf-125">En este caso, el parámetro de informe se incluye para especificar una ruta de acceso y un nombre de carpeta para el informe generado por la prueba.</span><span class="sxs-lookup"><span data-stu-id="a00cf-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="a00cf-126">Si no especifica una ruta de acceso al informe, se le proporcionará un nombre generado automáticamente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a00cf-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="a00cf-127">C:\\administrador\\de usuarios.\\litwareinc\\AppData\\local\\temporal\\1 prueba-CS-réplica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html</span><span class="sxs-lookup"><span data-stu-id="a00cf-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a00cf-128">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="a00cf-128">Determining success or failure</span></span>

<span data-ttu-id="a00cf-129">Inserte el cuerpo de la sección aquí.</span><span class="sxs-lookup"><span data-stu-id="a00cf-129">Insert section body here.</span></span>

<span data-ttu-id="a00cf-130">VERBOse: crear un nuevo archivo de registro "\\C\\:\\usuarios\\prueba\\AppData\\prueba de tiempo local-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="a00cf-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a00cf-131">VERBOse: crear un nuevo archivo de registro "\\C\\:\\usuarios\\prueba\\AppData\\prueba de tiempo local-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="a00cf-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a00cf-132">VERBOse: el procesamiento de "prueba-CsReplica" se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a00cf-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="a00cf-133">VERBOse puede encontrar los resultados detallados en "C\\:\\usuarios\\prueba\\AppData\\prueba\\local temporal-CsReplica-3cb066b3-dd23-411A-8932-99f01c0f940c. xml".</span><span class="sxs-lookup"><span data-stu-id="a00cf-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a00cf-134">VERBOse: crear un nuevo archivo de registro</span><span class="sxs-lookup"><span data-stu-id="a00cf-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="a00cf-135">"C:\\usuarios\\prueba\\AppData\\local\\temporal\\2\\prueba-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="a00cf-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a00cf-136">d3bd0e4a083. xml ".</span><span class="sxs-lookup"><span data-stu-id="a00cf-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="a00cf-137">VERBOse: crear un nuevo archivo de registro</span><span class="sxs-lookup"><span data-stu-id="a00cf-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="a00cf-138">"C:\\usuarios\\prueba\\AppData\\local\\temporal\\2\\prueba-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="a00cf-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a00cf-139">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="a00cf-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="a00cf-140">ADVERTENCIA: error de test-CsReplica.</span><span class="sxs-lookup"><span data-stu-id="a00cf-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="a00cf-141">ADVERTENCIA: puede encontrar resultados detallados en</span><span class="sxs-lookup"><span data-stu-id="a00cf-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="a00cf-142">"C:\\usuarios\\prueba\\AppData\\local\\temporal\\2\\prueba-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="a00cf-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a00cf-143">d3bd0e4a083. html ".</span><span class="sxs-lookup"><span data-stu-id="a00cf-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="a00cf-144">Prueba-CsReplica: error al ejecutar el comando: el acceso al registro solicitado no es</span><span class="sxs-lookup"><span data-stu-id="a00cf-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="a00cf-145">tienen.</span><span class="sxs-lookup"><span data-stu-id="a00cf-145">allowed.</span></span>

<span data-ttu-id="a00cf-146">En la línea: 1 carácter: 1</span><span class="sxs-lookup"><span data-stu-id="a00cf-146">At line:1 char:1</span></span>

<span data-ttu-id="a00cf-147">\+Prueba-CsReplica-verbose</span><span class="sxs-lookup"><span data-stu-id="a00cf-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="a00cf-148">\+CategoryInfo: InvalidOperation: (:) \[Prueba-CsReplica\], seguridad</span><span class="sxs-lookup"><span data-stu-id="a00cf-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="a00cf-149">Excepción</span><span class="sxs-lookup"><span data-stu-id="a00cf-149">Exception</span></span>

<span data-ttu-id="a00cf-150">\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="a00cf-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="a00cf-151">asignaciones. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="a00cf-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="a00cf-152">Prueba de PS\\C\\: usuarios\></span><span class="sxs-lookup"><span data-stu-id="a00cf-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="a00cf-153">PS C:\\usuarios\\probando\> prueba-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="a00cf-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="a00cf-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="a00cf-154">icrosoft.com"</span></span>

<span data-ttu-id="a00cf-155">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo</span><span class="sxs-lookup"><span data-stu-id="a00cf-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a00cf-156">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a00cf-156">domain name (FQDN).</span></span> <span data-ttu-id="a00cf-157">Usando el número de puerto predeterminado del registrador.</span><span class="sxs-lookup"><span data-stu-id="a00cf-157">Using default Registrar port number.</span></span> <span data-ttu-id="a00cf-158">Excepción</span><span class="sxs-lookup"><span data-stu-id="a00cf-158">Exception:</span></span>

<span data-ttu-id="a00cf-159">System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.</span><span class="sxs-lookup"><span data-stu-id="a00cf-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a00cf-160">en</span><span class="sxs-lookup"><span data-stu-id="a00cf-160">at</span></span>

<span data-ttu-id="a00cf-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="a00cf-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a00cf-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="a00cf-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a00cf-163">Prueba-CsUcwaConference: no hay ningún usuario de prueba asignado para</span><span class="sxs-lookup"><span data-stu-id="a00cf-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="a00cf-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="a00cf-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="a00cf-165">Comprobar la configuración del usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="a00cf-165">Verify test user configuration.</span></span>

<span data-ttu-id="a00cf-166">En la línea: 1 carácter: 1</span><span class="sxs-lookup"><span data-stu-id="a00cf-166">At line:1 char:1</span></span>

<span data-ttu-id="a00cf-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="a00cf-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="a00cf-168">\+CategoryInfo: ResourceUnavailable: (:) \[Prueba-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="a00cf-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="a00cf-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="a00cf-169">, InvalidOperationException</span></span>

<span data-ttu-id="a00cf-170">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador</span><span class="sxs-lookup"><span data-stu-id="a00cf-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="a00cf-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="a00cf-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a00cf-172">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="a00cf-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="a00cf-173">Estas son algunas de las razones comunes por las que **Test-CsReplica** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="a00cf-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="a00cf-174">Es posible que haya un problema mayor con el agente de replicación y los servicios de agente de registro centralizados</span><span class="sxs-lookup"><span data-stu-id="a00cf-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="a00cf-175">Es posible que los puertos necesarios no estén abiertos en el Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="a00cf-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="a00cf-176">Es posible que los grupos de seguridad de Active Directory y equipos locales necesarios no existan</span><span class="sxs-lookup"><span data-stu-id="a00cf-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

