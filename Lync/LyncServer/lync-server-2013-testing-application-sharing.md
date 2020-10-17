---
title: 'Lync Server 2013: prueba del uso compartido de aplicaciones'
description: 'Lync Server 2013: prueba del uso compartido de aplicaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560726"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="49a45-103">Prueba del uso compartido de aplicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a45-103">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a45-104">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="49a45-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a45-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="49a45-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="49a45-106">Diario</span><span class="sxs-lookup"><span data-stu-id="49a45-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a45-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="49a45-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="49a45-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49a45-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a45-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="49a45-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="49a45-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="49a45-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="49a45-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="49a45-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="49a45-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49a45-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="49a45-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="49a45-113">Description</span></span>

<span data-ttu-id="49a45-114">El cmdlet **Test-CsASConference** comprueba que un par de usuarios de prueba puedan participar en una conferencia en línea que incluya el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49a45-114">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="49a45-115">Para ello, el cmdlet registra los dos usuarios con Lync Server 2013 y, a continuación, usa una de las cuentas de usuario para crear una nueva Conferencia que incluye el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49a45-115">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="49a45-116">Luego, el cmdlet comprueba que el segundo usuario puede unirse a esa llamada de conferencia.</span><span class="sxs-lookup"><span data-stu-id="49a45-116">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="49a45-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="49a45-117">Running the test</span></span>

<span data-ttu-id="49a45-p103">El comando que se muestra en el ejemplo 1 comprueba que se puede llevar a cabo una conferencia de uso compartido de aplicaciones en el grupo atl-cs-001.litwareinc.com. Este comando asume que ha configurado un par de usuarios de prueba para el grupo especificado. Si los usuarios de prueba no existen, se producirá un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="49a45-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="49a45-p104">El ejemplo 2 comprueba la capacidad del servicio Join Launcher para participar en una conferencia de uso compartido de aplicaciones en el grupo atl-cs-001.litwareinc.com. Tenga en cuenta que este comando comprueba solo el servicio de sí mismo; no es necesario ningún dispositivo móvil para iniciar el comando.</span><span class="sxs-lookup"><span data-stu-id="49a45-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="49a45-123">Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par de usuarios (litwareinc \\ Pilar y litwareinc \\ kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, realizar una conferencia de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49a45-123">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="49a45-124">Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="49a45-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="49a45-125">(Como el nombre de inicio de sesión, litwareinc \\ pilar, se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). El objeto Credential resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="49a45-125">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="49a45-126">El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="49a45-126">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="49a45-127">Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y realizar una conferencia de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49a45-127">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="49a45-128">Para llevar a cabo esta tarea, se llama al cmdlet **Test-CsASConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de registrador); SenderSipAddress (la dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).</span><span class="sxs-lookup"><span data-stu-id="49a45-128">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="49a45-129">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="49a45-129">Determining success or failure</span></span>

<span data-ttu-id="49a45-130">Si el uso compartido de aplicaciones está configurado correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="49a45-130">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="49a45-131">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49a45-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="49a45-132">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="49a45-132">Result : Success</span></span>

<span data-ttu-id="49a45-133">Latencia: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="49a45-133">Latency : 00:00:01</span></span>

<span data-ttu-id="49a45-134">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="49a45-134">Error Message :</span></span>

<span data-ttu-id="49a45-135">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="49a45-135">Diagnosis :</span></span>

<span data-ttu-id="49a45-136">Si los usuarios especificados no pueden compartir aplicaciones, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="49a45-136">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="49a45-137">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49a45-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="49a45-138">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="49a45-138">Result : Failure</span></span>

<span data-ttu-id="49a45-139">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="49a45-139">Latency : 00:00:00</span></span>

<span data-ttu-id="49a45-140">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="49a45-140">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="49a45-141">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="49a45-141">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="49a45-142">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="49a45-142">established connection failed because connected host has</span></span>

<span data-ttu-id="49a45-143">no se pudo responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="49a45-143">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="49a45-144">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="49a45-144">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="49a45-145">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="49a45-145">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="49a45-146">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="49a45-146">time, or established connection failed because connected host</span></span>

<span data-ttu-id="49a45-147">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="49a45-147">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="49a45-148">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="49a45-148">Diagnosis :</span></span>

<span data-ttu-id="49a45-149">Por ejemplo, la salida anterior incluye la nota "la persona conectada no respondió correctamente" que normalmente indica un problema con el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="49a45-149">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="49a45-150">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="49a45-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="49a45-151">Estas son algunas de las razones comunes por las que **Test-CsASConference** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="49a45-151">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="49a45-152">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="49a45-152">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="49a45-153">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="49a45-153">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="49a45-154">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="49a45-154">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="49a45-155">Se producirá un error en este comando si a los usuarios de prueba se les asignó una directiva de conferencia que les impida usar el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49a45-155">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="49a45-156">Este comando producirá un error si el servidor perimetral está mal configurado o no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="49a45-156">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49a45-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49a45-157">See Also</span></span>


[<span data-ttu-id="49a45-158">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="49a45-158">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="49a45-159">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="49a45-159">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

