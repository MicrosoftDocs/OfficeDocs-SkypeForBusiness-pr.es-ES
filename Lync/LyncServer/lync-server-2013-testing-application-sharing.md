---
title: 'Lync Server 2013: probar el uso compartido de aplicaciones'
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
ms.openlocfilehash: ab428e5bbfb5ffc58fa7b1d092cd7fc04b117226
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="b20a0-102">Probar el uso compartido de aplicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b20a0-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b20a0-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b20a0-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b20a0-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="b20a0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b20a0-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="b20a0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b20a0-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="b20a0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b20a0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b20a0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b20a0-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="b20a0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b20a0-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b20a0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b20a0-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="b20a0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="b20a0-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b20a0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b20a0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b20a0-112">Description</span></span>

<span data-ttu-id="b20a0-113">El cmdlet **Test-CsASConference** comprueba que un par de usuarios de prueba pueden participar en una conferencia en línea que incluye el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b20a0-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="b20a0-114">Para ello, el cmdlet registra los dos usuarios con Lync Server 2013 y, a continuación, usa una de las cuentas de usuario para crear una nueva Conferencia que incluye el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b20a0-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="b20a0-115">El cmdlet comprueba entonces que el segundo usuario puede unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="b20a0-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b20a0-116">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="b20a0-116">Running the test</span></span>

<span data-ttu-id="b20a0-117">El comando que se muestra en el ejemplo 1 verifica que se puede realizar una conferencia de uso compartido de aplicaciones en el grupo atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b20a0-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b20a0-118">Este comando supone que ha configurado un par de usuarios de prueba para el grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="b20a0-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="b20a0-119">Si no existen esos usuarios de prueba, el comando fallará.</span><span class="sxs-lookup"><span data-stu-id="b20a0-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b20a0-120">El ejemplo 2 prueba la capacidad del servicio del iniciador de Unión para participar en una conferencia de uso compartido de aplicaciones en el grupo de atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b20a0-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b20a0-121">Ten en cuenta que este comando solo prueba el servicio en sí; no necesitas ningún dispositivo móvil para ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="b20a0-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="b20a0-122">Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par\\de usuarios (\\litwareinc Pilar y litwareinc kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, realizar una conferencia de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b20a0-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="b20a0-123">Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="b20a0-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="b20a0-124">(Como el nombre de inicio de\\sesión, litwareinc pilar, se ha incluido como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Pilar Ackerman). El objeto de credencial resultante se almacena en una variable llamada $cred 1.</span><span class="sxs-lookup"><span data-stu-id="b20a0-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="b20a0-125">El segundo comando hace lo mismo, pero esta vez devuelve un objeto de credenciales para la cuenta Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b20a0-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="b20a0-126">Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y realizar una conferencia de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b20a0-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="b20a0-127">Para llevar a cabo esta tarea, se llama al cmdlet **Test-CsASConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); SenderSipAddress (dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).</span><span class="sxs-lookup"><span data-stu-id="b20a0-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b20a0-128">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="b20a0-128">Determining success or failure</span></span>

<span data-ttu-id="b20a0-129">Si el uso compartido de aplicaciones está configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="b20a0-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b20a0-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b20a0-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b20a0-131">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="b20a0-131">Result : Success</span></span>

<span data-ttu-id="b20a0-132">Latencia: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="b20a0-132">Latency : 00:00:01</span></span>

<span data-ttu-id="b20a0-133">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="b20a0-133">Error Message :</span></span>

<span data-ttu-id="b20a0-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b20a0-134">Diagnosis :</span></span>

<span data-ttu-id="b20a0-135">Si los usuarios especificados no pueden compartir aplicaciones, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="b20a0-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b20a0-136">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b20a0-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b20a0-137">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="b20a0-137">Result : Failure</span></span>

<span data-ttu-id="b20a0-138">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b20a0-138">Latency : 00:00:00</span></span>

<span data-ttu-id="b20a0-139">Mensaje de error: 10060, error al intentar la conexión porque la persona conectada</span><span class="sxs-lookup"><span data-stu-id="b20a0-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b20a0-140">no respondió correctamente después de un período de tiempo, o</span><span class="sxs-lookup"><span data-stu-id="b20a0-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b20a0-141">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="b20a0-141">established connection failed because connected host has</span></span>

<span data-ttu-id="b20a0-142">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b20a0-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b20a0-143">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="b20a0-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b20a0-144">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="b20a0-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b20a0-145">hora o error de conexión establecida porque el host conectado</span><span class="sxs-lookup"><span data-stu-id="b20a0-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b20a0-146">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b20a0-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b20a0-147">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b20a0-147">Diagnosis :</span></span>

<span data-ttu-id="b20a0-148">Por ejemplo, la salida anterior incluye la nota "la persona conectada no respondió correctamente" que normalmente indica que hay un problema con el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b20a0-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b20a0-149">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="b20a0-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="b20a0-150">Estas son algunas de las razones comunes por las que **Test-CsASConference** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="b20a0-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="b20a0-151">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="b20a0-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b20a0-152">Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="b20a0-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b20a0-153">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="b20a0-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b20a0-154">Este comando producirá un error si se asignó una directiva de conferencia a los usuarios de prueba que les impide usar el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b20a0-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="b20a0-155">Este comando fallará si el servidor perimetral está mal configurado o aún no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="b20a0-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b20a0-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="b20a0-156">See Also</span></span>


[<span data-ttu-id="b20a0-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="b20a0-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="b20a0-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="b20a0-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

