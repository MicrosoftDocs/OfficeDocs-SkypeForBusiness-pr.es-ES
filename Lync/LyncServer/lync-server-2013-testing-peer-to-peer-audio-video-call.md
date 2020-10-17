---
title: 'Lync Server 2013: prueba de una llamada de audio o vídeo punto a punto'
description: 'Lync Server 2013: prueba de la llamada de audio o vídeo punto a punto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bab69d926a99c091a510ce64b78dbf505d4cbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556296"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="2f5f5-103">Probar la llamada de audio y vídeo de punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f5-103">Testing peer to peer audio/video call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f5f5-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2f5f5-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f5f5-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="2f5f5-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2f5f5-106">Diario</span><span class="sxs-lookup"><span data-stu-id="2f5f5-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f5f5-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="2f5f5-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2f5f5-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f5f5-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f5f5-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="2f5f5-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2f5f5-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2f5f5-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsP2PAV.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="2f5f5-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2f5f5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f5f5-113">Description</span></span>

<span data-ttu-id="2f5f5-114">Test-CsP2PAV se usa para determinar si un par de usuarios de prueba pueden participar en una conversación A/V de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-114">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="2f5f5-115">Para probar este escenario, el cmdlet se inicia al iniciar sesión en los dos usuarios en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-115">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="2f5f5-116">Suponiendo que los dos inicios de sesión se hayan realizado correctamente, el primer usuario invita al segundo usuario a unirse a una llamada de A/V.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-116">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="2f5f5-117">El segundo usuario acepta la llamada, se prueba la conexión entre los dos usuarios y, a continuación, finaliza la llamada y se cierra la sesión de los usuarios de prueba desde el sistema.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-117">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="2f5f5-118">Test-CsP2PAV no realiza realmente una llamada A/V.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-118">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="2f5f5-119">La información multimedia no se intercambiará entre los usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-119">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="2f5f5-120">En su lugar, el cmdlet simplemente comprueba que se pueden realizar las conexiones adecuadas y que los dos usuarios pueden realizar dicha llamada.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-120">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="2f5f5-121">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="2f5f5-121">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2f5f5-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="2f5f5-122">Running the test</span></span>

<span data-ttu-id="2f5f5-123">El cmdlet Test-CsP2PAV puede ejecutarse con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-123">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="2f5f5-124">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-124">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="2f5f5-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-125">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="2f5f5-126">Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Lync Server (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-126">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="2f5f5-127">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsP2PAV:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-127">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2f5f5-128">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="2f5f5-128">Determining success or failure</span></span>

<span data-ttu-id="2f5f5-129">Si los dos usuarios de prueba pueden completar una llamada a/V de punto a punto, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="2f5f5-129">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2f5f5-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2f5f5-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2f5f5-131">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="2f5f5-131">Result : Success</span></span>

<span data-ttu-id="2f5f5-132">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="2f5f5-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="2f5f5-133">Error</span><span class="sxs-lookup"><span data-stu-id="2f5f5-133">Error :</span></span>

<span data-ttu-id="2f5f5-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2f5f5-134">Diagnosis :</span></span>

<span data-ttu-id="2f5f5-135">Si los usuarios de prueba no pueden completar la llamada, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-135">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2f5f5-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2f5f5-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2f5f5-137">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="2f5f5-137">Result : Failure</span></span>

<span data-ttu-id="2f5f5-138">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="2f5f5-138">Latency : 00:00:00</span></span>

<span data-ttu-id="2f5f5-139">Error: 480, temporalmente no disponible</span><span class="sxs-lookup"><span data-stu-id="2f5f5-139">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="2f5f5-140">Diagnosis: ErrorCode = 15030, Source = ATL-CS-001. litwareinc. com, Reason = failed</span><span class="sxs-lookup"><span data-stu-id="2f5f5-140">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="2f5f5-141">para enrutar a Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2f5f5-141">to route to Exchange Server</span></span>

<span data-ttu-id="2f5f5-142">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="2f5f5-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="2f5f5-143">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se pudo establecer contacto con el servidor de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-143">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="2f5f5-144">Este mensaje de error suele indicar un problema con la configuración de la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-144">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="2f5f5-145">Si Test-CsP2PAV da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-145">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="2f5f5-146">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com": detallado</span><span class="sxs-lookup"><span data-stu-id="2f5f5-146">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="2f5f5-147">Cuando se incluye el parámetro verbose, Test-CsP2PAV devolverá una cuenta paso a paso por cada acción que se intentó, ya que se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-147">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2f5f5-148">Por ejemplo, supongamos que la prueba ha fallado con el siguiente diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-148">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="2f5f5-149">ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, causa = no se admite fuera de la solicitud de cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="2f5f5-149">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="2f5f5-150">Si vuelve a ejecutar Test-CsP2PAV e incluye el parámetro verbose, obtendrá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-150">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="2f5f5-151">VERBOse: Activity "Register" (registro) iniciada.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-151">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="2f5f5-152">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-152">Sending Registration request:</span></span>

<span data-ttu-id="2f5f5-153">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2f5f5-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="2f5f5-154">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2f5f5-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="2f5f5-155">Puerto del registrador = 5062.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-155">Registrar Port = 5062.</span></span>

<span data-ttu-id="2f5f5-156">El tipo de autenticación "IWA" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="2f5f5-157">Una excepción ' el punto de conexión no se pudo registrar.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-157">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="2f5f5-158">Consulte ErrorCode por motivos específicos. '</span><span class="sxs-lookup"><span data-stu-id="2f5f5-158">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="2f5f5-159">se produjeron durante la ejecución del flujo de trabajo Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-159">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="2f5f5-160">Aunque es posible que no sea obvio inmediatamente, si examina el resultado con cuidado, verá que se ha especificado un puerto registrado incorrecto (puerto 5062).</span><span class="sxs-lookup"><span data-stu-id="2f5f5-160">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="2f5f5-161">A su vez, esto provocaba un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-161">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2f5f5-162">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="2f5f5-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="2f5f5-163">Estas son algunas de las razones comunes por las que Test-CsP2PAV podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-163">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="2f5f5-164">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="2f5f5-165">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="2f5f5-166">Get-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="2f5f5-166">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="2f5f5-167">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-167">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2f5f5-168">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f5f5-168">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2f5f5-169">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f5f5-169">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

