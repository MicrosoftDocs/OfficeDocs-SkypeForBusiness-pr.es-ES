---
title: 'Lync Server 2013: capacidad de prueba para realizar la mensajería instantánea en grupo'
description: 'Lync Server 2013: capacidad de prueba para realizar la mensajería instantánea en grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6988a0c1a7ba569f7b4da098ae741beab5e14fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560816"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="529ce-103">Capacidad de prueba para hacer grupo de mensajería instantánea en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="529ce-103">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="529ce-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="529ce-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="529ce-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="529ce-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="529ce-106">Diario</span><span class="sxs-lookup"><span data-stu-id="529ce-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="529ce-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="529ce-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="529ce-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="529ce-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="529ce-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="529ce-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="529ce-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="529ce-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="529ce-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="529ce-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="529ce-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="529ce-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="529ce-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="529ce-113">Description</span></span>

<span data-ttu-id="529ce-114">El cmdlet Test-CsGroupIM comprueba que los usuarios de la organización pueden realizar sesiones de mensajería instantánea en grupo.</span><span class="sxs-lookup"><span data-stu-id="529ce-114">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="529ce-115">Al ejecutar test-CsGroupIM, el cmdlet intenta iniciar sesión en un par de usuarios de prueba para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="529ce-115">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="529ce-116">Si el resultado es correcto, Test-CsGroupIM crea una nueva conferencia con el primer usuario de prueba y, a continuación, invita al segundo usuario a unirse a ella.</span><span class="sxs-lookup"><span data-stu-id="529ce-116">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="529ce-117">Después de un intercambio de mensajes, se desconecta del sistema a ambos usuarios.</span><span class="sxs-lookup"><span data-stu-id="529ce-117">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="529ce-118">Tenga en cuenta que todo esto ocurre sin interacción del usuario y sin afectar a los usuarios reales.</span><span class="sxs-lookup"><span data-stu-id="529ce-118">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="529ce-119">Por ejemplo, supongamos que el sip:kenmyer@litwareinc.com de la cuenta de prueba corresponde a un usuario real que tiene una cuenta real de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="529ce-119">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="529ce-120">En ese caso, la prueba se realizará sin ningún tipo de interrupción ocasionada al Ken Myer real.</span><span class="sxs-lookup"><span data-stu-id="529ce-120">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="529ce-121">Por ejemplo, aunque la cuenta de prueba de Ken Myer cierre sesión en el sistema, Ken Myer, la persona, permanecerá conectado.</span><span class="sxs-lookup"><span data-stu-id="529ce-121">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="529ce-122">Del mismo modo, el auténtico Ken Myer no recibirá una invitación para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="529ce-122">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="529ce-123">Dicha invitación se enviará a la cuenta de prueba y será esta la que aceptará.</span><span class="sxs-lookup"><span data-stu-id="529ce-123">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="529ce-124">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="529ce-124">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="529ce-125">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="529ce-125">Running the test</span></span>

<span data-ttu-id="529ce-126">El cmdlet Test-CsGroupIM puede ejecutarse con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="529ce-126">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="529ce-127">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="529ce-127">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="529ce-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="529ce-128">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="529ce-129">Para ejecutar esta comprobación mediante cuentas de usuario reales, debe crear dos objetos de credenciales del shell de administración de Lync Server (objetos que contengan el nombre y la contraseña de la cuenta) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="529ce-129">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="529ce-130">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="529ce-130">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="529ce-131">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="529ce-131">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="529ce-132">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="529ce-132">Determining Success or Failure</span></span>

<span data-ttu-id="529ce-133">Si los dos usuarios pueden completar una sesión de mensajería instantánea de grupo, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="529ce-133">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="529ce-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="529ce-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="529ce-135">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="529ce-135">Result : Success</span></span>

<span data-ttu-id="529ce-136">Latencia: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="529ce-136">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="529ce-137">Error</span><span class="sxs-lookup"><span data-stu-id="529ce-137">Error :</span></span>

<span data-ttu-id="529ce-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="529ce-138">Diagnosis :</span></span>

<span data-ttu-id="529ce-139">Si los dos usuarios no pueden completar la sesión de mensajería instantánea, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="529ce-139">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="529ce-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="529ce-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="529ce-141">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="529ce-141">Result : Failure</span></span>

<span data-ttu-id="529ce-142">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="529ce-142">Latency : 00:00:00</span></span>

<span data-ttu-id="529ce-143">Error: 404, no encontrado</span><span class="sxs-lookup"><span data-stu-id="529ce-143">Error : 404, Not Found</span></span>

<span data-ttu-id="529ce-144">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="529ce-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="529ce-145">Razón = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="529ce-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="529ce-146">haber.</span><span class="sxs-lookup"><span data-stu-id="529ce-146">exist.</span></span>

<span data-ttu-id="529ce-147">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="529ce-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="529ce-148">La salida anterior indica que se produjo un error en la prueba porque al menos una de las cuentas de prueba no era válida, ya sea porque la cuenta no existe o porque el usuario no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="529ce-148">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="529ce-149">Puede comprobar que la cuenta existe y si la cuenta está habilitada para nm-OCS-14-3rd ejecutando un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="529ce-149">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="529ce-150">Si Test-CsGroupIM da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="529ce-150">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="529ce-151">Cuando se incluye el parámetro verbose, Test-CsGroupIM devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad de los usuarios especificados para participar en una sesión de mensajería instantánea de grupo.</span><span class="sxs-lookup"><span data-stu-id="529ce-151">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="529ce-152">Por ejemplo, si se produce un error en la prueba y se le indica que una o varias cuentas de usuario no son válidas, puede volver a ejecutar la prueba con el parámetro verbose y determinar qué cuenta de usuario no es válida:</span><span class="sxs-lookup"><span data-stu-id="529ce-152">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="529ce-153">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="529ce-153">Sending Registration request:</span></span>

 <span data-ttu-id="529ce-154">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="529ce-154">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="529ce-155">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="529ce-155">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="529ce-156">Puerto de registro = 5061</span><span class="sxs-lookup"><span data-stu-id="529ce-156">Register Port    = 5061</span></span>

<span data-ttu-id="529ce-157">El tipo de autenticación "IWA" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="529ce-157">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="529ce-158">Excepción: "se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="529ce-158">An exception 'The log on was denied.</span></span> <span data-ttu-id="529ce-159">Compruebe que se usan las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="529ce-159">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="529ce-160">Como puede ver, en este ejemplo, el usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com no pudo iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="529ce-160">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="529ce-161">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="529ce-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="529ce-162">Estas son algunas de las razones comunes por las que Test-CsGroupIM podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="529ce-162">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="529ce-163">Ha especificado una cuenta de usuario incorrecta.</span><span class="sxs-lookup"><span data-stu-id="529ce-163">You specified an incorrect user account.</span></span> <span data-ttu-id="529ce-164">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="529ce-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="529ce-165">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="529ce-165">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="529ce-166">Para comprobar que una cuenta de usuario se habilitó para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="529ce-166">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="529ce-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object habilitado</span><span class="sxs-lookup"><span data-stu-id="529ce-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="529ce-168">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="529ce-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="529ce-169">Es posible que el servicio de mensajería instantánea no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="529ce-169">The instant messaging service might not be available.</span></span> <span data-ttu-id="529ce-170">Con Lync Server, puede configurar el sistema para que la mensajería instantánea no esté disponible si no se puede tener acceso a la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="529ce-170">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="529ce-171">Puede comprobar si ejecuta un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="529ce-171">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="529ce-172">Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="529ce-172">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="529ce-173">Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="529ce-173">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="529ce-174">Es posible que el servidor de archivado no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="529ce-174">The Archiving Server might not be available.</span></span> <span data-ttu-id="529ce-175">Puede recuperar el FQDN de los servidores de archivado con este comando:</span><span class="sxs-lookup"><span data-stu-id="529ce-175">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="529ce-176">A continuación, puede hacer ping en el servidor adecuado para comprobar que está disponible.</span><span class="sxs-lookup"><span data-stu-id="529ce-176">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="529ce-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="529ce-177">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

