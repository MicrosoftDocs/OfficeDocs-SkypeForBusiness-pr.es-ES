---
title: 'Lync Server 2013: capacidad de pruebas para realizar conversaciones grupales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="d881c-102">Capacidad de pruebas para realizar una conversación grupal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d881c-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d881c-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d881c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d881c-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="d881c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d881c-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="d881c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d881c-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="d881c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d881c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d881c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d881c-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="d881c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d881c-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d881c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d881c-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsGroupIM.</span><span class="sxs-lookup"><span data-stu-id="d881c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="d881c-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d881c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d881c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d881c-112">Description</span></span>

<span data-ttu-id="d881c-113">El cmdlet test-CsGroupIM verifica que los usuarios de su organización puedan realizar sesiones grupales de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="d881c-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="d881c-114">Al ejecutar test-CsGroupIM, el cmdlet intenta iniciar sesión en un par de usuarios de prueba para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d881c-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="d881c-115">Si se realiza correctamente, test-CsGroupIM crea una nueva conferencia con el primer usuario de prueba y, a continuación, invita al segundo usuario a unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d881c-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="d881c-116">Después de un intercambio de mensajes, ambos usuarios se desconectan del sistema.</span><span class="sxs-lookup"><span data-stu-id="d881c-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="d881c-117">Tenga en cuenta que todo esto se produce sin la intervención del usuario y sin afectar a los usuarios reales.</span><span class="sxs-lookup"><span data-stu-id="d881c-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="d881c-118">Por ejemplo, supongamos que el sip:kenmyer@litwareinc.com de la cuenta de prueba corresponde a un usuario real que tiene una cuenta real de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d881c-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="d881c-119">En ese caso, la prueba se realizará sin interrupciones en real Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d881c-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="d881c-120">Por ejemplo, incluso cuando la cuenta de prueba Ken Myer cierra la sesión desde el sistema, Ken Myer la persona permanecerá conectada.</span><span class="sxs-lookup"><span data-stu-id="d881c-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="d881c-121">Del mismo modo, los verdaderos Ken Myer no recibirán una invitación para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d881c-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="d881c-122">La invitación se enviará a la cuenta de prueba y la aceptará.</span><span class="sxs-lookup"><span data-stu-id="d881c-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="d881c-123">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="d881c-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d881c-124">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="d881c-124">Running the test</span></span>

<span data-ttu-id="d881c-125">El cmdlet test-CsGroupIM se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d881c-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d881c-126">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando.</span><span class="sxs-lookup"><span data-stu-id="d881c-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d881c-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d881c-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d881c-128">Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales del shell de administración de Lync Server (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="d881c-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d881c-129">Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsGroupIM:</span><span class="sxs-lookup"><span data-stu-id="d881c-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="d881c-130">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="d881c-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d881c-131">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="d881c-131">Determining Success or Failure</span></span>

<span data-ttu-id="d881c-132">Si los dos usuarios pueden completar una sesión de mensajería instantánea grupal, recibirá un resultado similar a este con la propiedad resultado marcada como **correcto:**</span><span class="sxs-lookup"><span data-stu-id="d881c-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d881c-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d881c-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d881c-134">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="d881c-134">Result : Success</span></span>

<span data-ttu-id="d881c-135">Latencia: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="d881c-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="d881c-136">:</span><span class="sxs-lookup"><span data-stu-id="d881c-136">Error :</span></span>

<span data-ttu-id="d881c-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d881c-137">Diagnosis :</span></span>

<span data-ttu-id="d881c-138">Si los dos usuarios no pueden completar la sesión de mensajería instantánea, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d881c-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d881c-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d881c-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d881c-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="d881c-140">Result : Failure</span></span>

<span data-ttu-id="d881c-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d881c-141">Latency : 00:00:00</span></span>

<span data-ttu-id="d881c-142">Error: 404, no se encontró</span><span class="sxs-lookup"><span data-stu-id="d881c-142">Error : 404, Not Found</span></span>

<span data-ttu-id="d881c-143">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="d881c-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="d881c-144">Motivo = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="d881c-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="d881c-145">condiciones.</span><span class="sxs-lookup"><span data-stu-id="d881c-145">exist.</span></span>

<span data-ttu-id="d881c-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d881c-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d881c-147">El resultado anterior indica que la prueba no se realizó correctamente porque al menos una de las cuentas de prueba no era válida, ya sea porque la cuenta no existe o porque el usuario no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d881c-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="d881c-148">Puede comprobar si la cuenta existe y si la cuenta ha sido habilitada para nm-OCS-14-3rd ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="d881c-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="d881c-149">Si prueba-CsGroupIM da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="d881c-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="d881c-150">Cuando se incluye el parámetro detallado, test-CsGroupIM devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad de los usuarios especificados para participar en una sesión de mensajería instantánea grupal.</span><span class="sxs-lookup"><span data-stu-id="d881c-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="d881c-151">Por ejemplo, si se produce un error en la prueba y se dice que una o varias de las cuentas de usuario no son válidas, puede volver a ejecutar la prueba con el parámetro detallado y determinar qué cuenta de usuario no es válida:</span><span class="sxs-lookup"><span data-stu-id="d881c-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="d881c-152">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="d881c-152">Sending Registration request:</span></span>

 <span data-ttu-id="d881c-153">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d881c-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="d881c-154">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d881c-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="d881c-155">Registrar puerto = 5061</span><span class="sxs-lookup"><span data-stu-id="d881c-155">Register Port    = 5061</span></span>

<span data-ttu-id="d881c-156">El tipo de autenticación ' IWA ' está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d881c-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="d881c-157">Excepción ' se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="d881c-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="d881c-158">Compruebe que se están usando las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="d881c-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="d881c-159">Como puede ver, en este ejemplo, el usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com no pudo iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="d881c-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d881c-160">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="d881c-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="d881c-161">Estas son algunas de las razones comunes por las que test-CsGroupIM podría fallar:</span><span class="sxs-lookup"><span data-stu-id="d881c-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="d881c-162">Ha especificado una cuenta de usuario incorrecta.</span><span class="sxs-lookup"><span data-stu-id="d881c-162">You specified an incorrect user account.</span></span> <span data-ttu-id="d881c-163">Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="d881c-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d881c-164">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d881c-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d881c-165">Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d881c-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="d881c-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Seleccionar-objeto habilitado</span><span class="sxs-lookup"><span data-stu-id="d881c-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="d881c-167">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d881c-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d881c-168">Es posible que el servicio de mensajería instantánea no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d881c-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="d881c-169">Con Lync Server, puede configurar el sistema para que la mensajería instantánea no esté disponible si no se puede obtener acceso a la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="d881c-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="d881c-170">Puede comprobar que al ejecutar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d881c-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="d881c-171">Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="d881c-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="d881c-172">Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d881c-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="d881c-173">Es posible que el servidor de archivado no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d881c-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="d881c-174">Puede recuperar el FQDN de los servidores de archivado con este comando:</span><span class="sxs-lookup"><span data-stu-id="d881c-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="d881c-175">Después, puede hacer ping al servidor apropiado para comprobar que está disponible.</span><span class="sxs-lookup"><span data-stu-id="d881c-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="d881c-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d881c-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

