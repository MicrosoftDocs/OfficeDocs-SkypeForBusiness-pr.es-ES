---
title: 'Lync Server 2013: probar conferencias de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af4bd6dd911b43714dffa48c3b21d3329b2aaa01
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="fe92a-102">Probar conferencias de UCWA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe92a-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe92a-103">_**Última modificación del tema:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="fe92a-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe92a-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="fe92a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fe92a-105">Diario</span><span class="sxs-lookup"><span data-stu-id="fe92a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe92a-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="fe92a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fe92a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe92a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe92a-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="fe92a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fe92a-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fe92a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fe92a-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsUcwaConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="fe92a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="fe92a-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fe92a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fe92a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe92a-112">Description</span></span>

<span data-ttu-id="fe92a-113">El cmdlet **Test-CsUcwaConference** comprueba que un par de usuarios de prueba puedan programar, unirse y realizar una conferencia en línea mediante la API Web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="fe92a-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="fe92a-114">Para ello, el cmdlet usa el servicio de vale Web de Lync Server para autenticar los dos usuarios de prueba y registrarlos con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe92a-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="fe92a-115">A continuación, el cmdlet inicia una conferencia usando las credenciales de organizador e invita al participante a incorporarse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="fe92a-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="fe92a-116">Una vez que se ha unido la reunión, el cmdlet **Test-CsUcwaConference** comprueba que los usuarios pueden hacer cosas como mensajes instantáneos de Exchange y realizar grupos de servidores y, a continuación, desconectar la Conferencia y anular el registro de los dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="fe92a-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="fe92a-117">La Conferencia programada también se eliminará cuando finalice la prueba.</span><span class="sxs-lookup"><span data-stu-id="fe92a-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="fe92a-118">El cmdlet **Test-CsUcwaConference** también se puede usar para determinar si los usuarios anónimos pueden unirse a conferencias en línea.</span><span class="sxs-lookup"><span data-stu-id="fe92a-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="fe92a-119">Tenga en cuenta que el cmdlet **Test-CsUcwaConference** no debe ejecutarse en un grupo de servidores de Microsoft Lync Server 2010 a menos que se haya instalado UCWA en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="fe92a-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="fe92a-120">Si no se ha instalado UCWA, se producirá un error en la llamada al cmdlet **Test-CsUcwaConference** .</span><span class="sxs-lookup"><span data-stu-id="fe92a-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fe92a-121">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="fe92a-121">Running the test</span></span>

<span data-ttu-id="fe92a-p104">El comando que se muestra en el Ejemplo 1 comprueba que un par de usuarios de prueba pueden participar en una conferencia UCWA en el grupo atl-cs-001.litwareinc.com. Tenga en cuenta que este comando dará error si no ha predefinido un par de usuarios de prueba de configuración de seguimiento de estado en atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fe92a-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="fe92a-124">Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par\\de usuarios (\\litwareinc Pilar y litwareinc kenmyer) para participar en una conferencia de UCWA.</span><span class="sxs-lookup"><span data-stu-id="fe92a-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="fe92a-125">Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="fe92a-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="fe92a-126">(Como el nombre de inicio de\\sesión, litwareinc pilar, se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). A continuación, el objeto de credenciales resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="fe92a-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="fe92a-127">El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="fe92a-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="fe92a-128">Con los dos objetos de credenciales a mano, el tercer comando del ejemplo determina si los dos usuarios pueden participar en una conferencia de UCWA.</span><span class="sxs-lookup"><span data-stu-id="fe92a-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="fe92a-129">Para ejecutar esta tarea, se llama al cmdlet **Test-CsUcwaConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de registrador); OrganizerSipAddress (la dirección SIP del organizador de la reunión); OrganizerCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ParticipantSipAddress (la dirección SIP del otro usuario de prueba); y ParticipantCredential (el objeto de la interfaz de línea de comandos de Windows PowerShell que contiene las credenciales del otro usuario).</span><span class="sxs-lookup"><span data-stu-id="fe92a-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fe92a-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="fe92a-130">Determining success or failure</span></span>

<span data-ttu-id="fe92a-131">Si la Conferencia está configurada correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="fe92a-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fe92a-132">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fe92a-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fe92a-133">URI de destino: https://LyncTest-SE. LyncTest. SelfHost. Corp.</span><span class="sxs-lookup"><span data-stu-id="fe92a-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="fe92a-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="fe92a-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="fe92a-135">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="fe92a-135">Result : Success</span></span>

<span data-ttu-id="fe92a-136">Latencia: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="fe92a-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="fe92a-137">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="fe92a-137">Error Message :</span></span>

<span data-ttu-id="fe92a-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="fe92a-138">Diagnosis :</span></span>

<span data-ttu-id="fe92a-139">Si los usuarios especificados no pueden usar la Conferencia, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="fe92a-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fe92a-140">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="fe92a-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="fe92a-141">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="fe92a-141">domain name (FQDN).</span></span> <span data-ttu-id="fe92a-142">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fe92a-142">Using default Registrar port number.</span></span> <span data-ttu-id="fe92a-143">Excepción</span><span class="sxs-lookup"><span data-stu-id="fe92a-143">Exception:</span></span>

<span data-ttu-id="fe92a-144">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="fe92a-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="fe92a-145">Veamos</span><span class="sxs-lookup"><span data-stu-id="fe92a-145">at</span></span>

<span data-ttu-id="fe92a-146">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="fe92a-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="fe92a-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="fe92a-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="fe92a-148">Test-CsUcwaConference: no hay ningún usuario de prueba asignado para</span><span class="sxs-lookup"><span data-stu-id="fe92a-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="fe92a-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="fe92a-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="fe92a-150">Compruebe la configuración del usuario de prueba.</span><span class="sxs-lookup"><span data-stu-id="fe92a-150">Verify test user configuration.</span></span>

<span data-ttu-id="fe92a-151">En la línea: 1 carácter: 1</span><span class="sxs-lookup"><span data-stu-id="fe92a-151">At line:1 char:1</span></span>

<span data-ttu-id="fe92a-152">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="fe92a-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="fe92a-153">\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="fe92a-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="fe92a-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="fe92a-154">, InvalidOperationException</span></span>

<span data-ttu-id="fe92a-155">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador</span><span class="sxs-lookup"><span data-stu-id="fe92a-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="fe92a-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="fe92a-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fe92a-157">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="fe92a-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="fe92a-158">Estas son algunas de las razones comunes por las que **Test-CsUcwaConference** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="fe92a-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="fe92a-159">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="fe92a-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="fe92a-160">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="fe92a-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="fe92a-161">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="fe92a-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="fe92a-162">La capacidad de realizar una conferencia depende de la Directiva de conferencia asignada al usuario que organizó la Conferencia (en el caso del cmdlet **Test-CsUcwaConference** , que es el "remitente").</span><span class="sxs-lookup"><span data-stu-id="fe92a-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="fe92a-163">Si el organizador no puede incluir actividades colaborativas en su reunión (por ejemplo, si su Directiva de conferencia tiene la propiedad EnableDataCollaboration establecida en false), se producirá un error en el cmdlet **Test-CsUcwaConference** .</span><span class="sxs-lookup"><span data-stu-id="fe92a-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="fe92a-164">Este comando producirá un error si el servidor perimetral está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="fe92a-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe92a-165">Consulta también</span><span class="sxs-lookup"><span data-stu-id="fe92a-165">See Also</span></span>


[<span data-ttu-id="fe92a-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="fe92a-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="fe92a-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="fe92a-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="fe92a-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="fe92a-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

