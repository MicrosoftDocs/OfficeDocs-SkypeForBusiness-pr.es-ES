---
title: 'Lync Server 2013: prueba del servicio de réplicas'
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
ms.openlocfilehash: e30d0b8c0e570605c8c6556d42224a205741a821
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503969"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="c79a8-102">Probar el servicio de réplicas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c79a8-102">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c79a8-103">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c79a8-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c79a8-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="c79a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c79a8-105">Diario</span><span class="sxs-lookup"><span data-stu-id="c79a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c79a8-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="c79a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c79a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c79a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c79a8-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c79a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c79a8-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c79a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c79a8-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsReplica</strong> .</span><span class="sxs-lookup"><span data-stu-id="c79a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="c79a8-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c79a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c79a8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c79a8-112">Description</span></span>

<span data-ttu-id="c79a8-113">El cmdlet **Test-CsReplica** comprueba que el servicio de réplica de 2013 de Lync Server se está ejecutando en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="c79a8-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="c79a8-114">El cmdlet **Test-CsReplica** realiza tareas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c79a8-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="c79a8-115">comprobación del estado del agente de replicador y los servicios de agente de registro centralizados</span><span class="sxs-lookup"><span data-stu-id="c79a8-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="c79a8-116">comprobar que los puertos necesarios se abrieron en el Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="c79a8-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="c79a8-117">asegurándose de que existen los grupos de seguridad de Active Directory y de equipo local necesarios.</span><span class="sxs-lookup"><span data-stu-id="c79a8-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="c79a8-118">Tenga en cuenta que este cmdlet debe ejecutarse de forma local.</span><span class="sxs-lookup"><span data-stu-id="c79a8-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="c79a8-119">Es decir, debe ejecutarse en el mismo equipo en el que se ejecuta el servicio de réplicas.</span><span class="sxs-lookup"><span data-stu-id="c79a8-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="c79a8-120">No hay opciones para ejecutar el cmdlet **Test-CsReplica** en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="c79a8-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c79a8-121">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="c79a8-121">Running the test</span></span>

<span data-ttu-id="c79a8-122">El comando que se muestra en el ejemplo 1 prueba el servicio de réplica de Lync Server 2013 en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="c79a8-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="c79a8-123">En este ejemplo, se usa el parámetro verbose para garantizar que la información sobre la prueba, incluido el error eventual o el éxito de la prueba, y la ubicación del informe generado por la prueba, se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="c79a8-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="c79a8-124">El ejemplo 2 es una variación del comando que se muestra en el ejemplo 1.</span><span class="sxs-lookup"><span data-stu-id="c79a8-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="c79a8-125">En este caso, el parámetro Report se incluye para especificar una ruta de acceso de carpeta y un nombre para el informe generado por la prueba.</span><span class="sxs-lookup"><span data-stu-id="c79a8-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="c79a8-126">Si no se especifica ninguna ruta de acceso para el informe, se le asignará un nombre generado automáticamente similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c79a8-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="c79a8-127">C: \\ usuario \\ Administrador. litwareinc \\ AppData \\ local \\ temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="c79a8-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c79a8-128">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="c79a8-128">Determining success or failure</span></span>

<span data-ttu-id="c79a8-129">Inserte el cuerpo de la sección aquí.</span><span class="sxs-lookup"><span data-stu-id="c79a8-129">Insert section body here.</span></span>

<span data-ttu-id="c79a8-130">VERBOse: creación de un nuevo archivo de registro "C: \\ usuarios \\ Testing \\ AppData \\ \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml temporales local \\ ".</span><span class="sxs-lookup"><span data-stu-id="c79a8-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c79a8-131">VERBOse: creación de un nuevo archivo de registro "C: \\ usuarios \\ Testing \\ AppData \\ \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml temporales local \\ ".</span><span class="sxs-lookup"><span data-stu-id="c79a8-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c79a8-132">VERBOse: el procesamiento de "test-CsReplica" se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c79a8-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="c79a8-133">VERBOse: los resultados detallados se pueden encontrar en "C: \\ users \\ Testing \\ AppData \\ local \\ temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span><span class="sxs-lookup"><span data-stu-id="c79a8-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c79a8-134">VERBOse: creación de un nuevo archivo de registro</span><span class="sxs-lookup"><span data-stu-id="c79a8-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="c79a8-135">"C: \\ usuarios \\ probando \\ AppData \\ local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="c79a8-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c79a8-136">d3bd0e4a083.xml ".</span><span class="sxs-lookup"><span data-stu-id="c79a8-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="c79a8-137">VERBOse: creación de un nuevo archivo de registro</span><span class="sxs-lookup"><span data-stu-id="c79a8-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="c79a8-138">"C: \\ usuarios \\ probando \\ AppData \\ local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="c79a8-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c79a8-139">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="c79a8-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="c79a8-140">ADVERTENCIA: error de Test-CsReplica.</span><span class="sxs-lookup"><span data-stu-id="c79a8-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="c79a8-141">ADVERTENCIA: los resultados detallados se pueden encontrar en</span><span class="sxs-lookup"><span data-stu-id="c79a8-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="c79a8-142">"C: \\ usuarios \\ probando \\ AppData \\ local \\ temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="c79a8-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c79a8-143">d3bd0e4a083.html ".</span><span class="sxs-lookup"><span data-stu-id="c79a8-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="c79a8-144">Test-CsReplica: error en la ejecución del comando: el acceso al registro solicitado no es</span><span class="sxs-lookup"><span data-stu-id="c79a8-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="c79a8-145">permiso.</span><span class="sxs-lookup"><span data-stu-id="c79a8-145">allowed.</span></span>

<span data-ttu-id="c79a8-146">En la línea: 1 carácter: 1</span><span class="sxs-lookup"><span data-stu-id="c79a8-146">At line:1 char:1</span></span>

<span data-ttu-id="c79a8-147">\+ Test-CsReplica-verbose</span><span class="sxs-lookup"><span data-stu-id="c79a8-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c79a8-148">\+ CategoryInfo: InvalidOperation: (:) \[ Test-CsReplica \] , seguridad</span><span class="sxs-lookup"><span data-stu-id="c79a8-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="c79a8-149">Excepción</span><span class="sxs-lookup"><span data-stu-id="c79a8-149">Exception</span></span>

<span data-ttu-id="c79a8-150">\+ FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy</span><span class="sxs-lookup"><span data-stu-id="c79a8-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="c79a8-151">Comentario. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="c79a8-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="c79a8-152">PS C: \\ usuarios \\ probar\></span><span class="sxs-lookup"><span data-stu-id="c79a8-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="c79a8-153">PS C: \\ usuarios que \\ prueban \> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost. Corp. M</span><span class="sxs-lookup"><span data-stu-id="c79a8-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="c79a8-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="c79a8-154">icrosoft.com"</span></span>

<span data-ttu-id="c79a8-155">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="c79a8-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c79a8-156">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="c79a8-156">domain name (FQDN).</span></span> <span data-ttu-id="c79a8-157">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c79a8-157">Using default Registrar port number.</span></span> <span data-ttu-id="c79a8-158">Excepción</span><span class="sxs-lookup"><span data-stu-id="c79a8-158">Exception:</span></span>

<span data-ttu-id="c79a8-159">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="c79a8-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c79a8-160">Veamos</span><span class="sxs-lookup"><span data-stu-id="c79a8-160">at</span></span>

<span data-ttu-id="c79a8-161">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="c79a8-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c79a8-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c79a8-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c79a8-163">Test-CsUcwaConference: no hay ningún usuario de prueba asignado para</span><span class="sxs-lookup"><span data-stu-id="c79a8-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="c79a8-164">\[LyncTest.SelfHost.Corp.Microsoft.com \] .</span><span class="sxs-lookup"><span data-stu-id="c79a8-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="c79a8-165">Compruebe la configuración del usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="c79a8-165">Verify test user configuration.</span></span>

<span data-ttu-id="c79a8-166">En la línea: 1 carácter: 1</span><span class="sxs-lookup"><span data-stu-id="c79a8-166">At line:1 char:1</span></span>

<span data-ttu-id="c79a8-167">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="c79a8-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c79a8-168">\+ CategoryInfo: ResourceUnavailable: (:) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="c79a8-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="c79a8-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="c79a8-169">, InvalidOperationException</span></span>

<span data-ttu-id="c79a8-170">\+ FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador</span><span class="sxs-lookup"><span data-stu-id="c79a8-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="c79a8-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="c79a8-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c79a8-172">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="c79a8-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="c79a8-173">Estas son algunas de las razones comunes por las que **Test-CsReplica** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="c79a8-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="c79a8-174">Es posible que haya un problema mayor con los servicios agente de duplicación y agente de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="c79a8-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="c79a8-175">Es posible que los puertos necesarios no estén abiertos en el Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="c79a8-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="c79a8-176">Es posible que no existan los grupos de seguridad de Active Directory y del equipo local necesarios</span><span class="sxs-lookup"><span data-stu-id="c79a8-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

