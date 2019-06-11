---
title: 'Lync Server 2013: Directiva de ubicación de pruebas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="29bfd-102">Probar la Directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29bfd-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29bfd-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="29bfd-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29bfd-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="29bfd-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29bfd-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="29bfd-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29bfd-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="29bfd-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29bfd-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29bfd-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29bfd-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="29bfd-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29bfd-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="29bfd-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29bfd-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="29bfd-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="29bfd-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29bfd-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29bfd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="29bfd-112">Description</span></span>

<span data-ttu-id="29bfd-113">El cmdlet test-CsLocationPolicy verifica que se asigne una directiva de ubicación a un usuario.</span><span class="sxs-lookup"><span data-stu-id="29bfd-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="29bfd-114">La Directiva de ubicación se usa para aplicar la configuración relacionada con la funcionalidad de E9-1-1 y la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="29bfd-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="29bfd-115">La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si la respuesta es "sí", cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="29bfd-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="29bfd-116">Por ejemplo, puede usar la política de ubicación para definir qué número constituye una llamada de emergencia (911 en los Estados Unidos), si se debe notificar automáticamente la seguridad corporativa y cómo se debe dirigir la llamada.</span><span class="sxs-lookup"><span data-stu-id="29bfd-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="29bfd-117">Puede probar las directivas de ubicación en los usuarios o en las subredes de la red.</span><span class="sxs-lookup"><span data-stu-id="29bfd-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="29bfd-118">Si ejecuta la prueba en una subred (especificando un valor para el parámetro de subred), el cmdlet intentará resolver la Directiva de ubicación de esa subred.</span><span class="sxs-lookup"><span data-stu-id="29bfd-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="29bfd-119">Si no se asigna ninguna directiva de ubicación a la subred, se recuperará la Directiva de ubicación del usuario configurado.</span><span class="sxs-lookup"><span data-stu-id="29bfd-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="29bfd-120">Si la Directiva de subred se recupera correctamente, la salida incluirá un valor LocationPolicyTagID que comienza con subnet-TagID.</span><span class="sxs-lookup"><span data-stu-id="29bfd-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="29bfd-121">Si no se encontró una directiva de ubicación para la subred, el LocationPolicyTagID comenzará con el usuario-TagID.</span><span class="sxs-lookup"><span data-stu-id="29bfd-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29bfd-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="29bfd-122">Running the test</span></span>

<span data-ttu-id="29bfd-123">El cmdlet test-CsLocationPolicy se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29bfd-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="29bfd-124">Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando.</span><span class="sxs-lookup"><span data-stu-id="29bfd-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="29bfd-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29bfd-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="29bfd-126">Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="29bfd-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="29bfd-127">Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="29bfd-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="29bfd-128">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="29bfd-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29bfd-129">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="29bfd-129">Determining success or failure</span></span>

<span data-ttu-id="29bfd-130">Si el usuario especificado tiene una directiva de ubicación válida, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="29bfd-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="29bfd-131">EnhancedEmergencyServicesEnabled: verdadero</span><span class="sxs-lookup"><span data-stu-id="29bfd-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="29bfd-132">LocationPolicyTagID: usuario-TagID</span><span class="sxs-lookup"><span data-stu-id="29bfd-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="29bfd-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29bfd-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29bfd-134">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="29bfd-134">Result : Success</span></span>

<span data-ttu-id="29bfd-135">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="29bfd-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="29bfd-136">:</span><span class="sxs-lookup"><span data-stu-id="29bfd-136">Error :</span></span>

<span data-ttu-id="29bfd-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="29bfd-137">Diagnosis :</span></span>

<span data-ttu-id="29bfd-138">Si no se puede encontrar una directiva de ubicación válida para el usuario especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="29bfd-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="29bfd-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29bfd-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29bfd-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="29bfd-140">Result : Failure</span></span>

<span data-ttu-id="29bfd-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="29bfd-141">Latency : 00:00:00</span></span>

<span data-ttu-id="29bfd-142">Error: 404, no se encontró</span><span class="sxs-lookup"><span data-stu-id="29bfd-142">Error : 404, Not Found</span></span>

<span data-ttu-id="29bfd-143">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="29bfd-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="29bfd-144">Motivo = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="29bfd-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="29bfd-145">condiciones.</span><span class="sxs-lookup"><span data-stu-id="29bfd-145">exist.</span></span>

<span data-ttu-id="29bfd-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="29bfd-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="29bfd-147">El resultado anterior indica que se produjo un error en la prueba porque el usuario especificado no es válido: la cuenta no existe o el usuario no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29bfd-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="29bfd-148">Puede comprobar la validez de una cuenta y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="29bfd-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="29bfd-149">Si prueba-CsLocationPolicy da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="29bfd-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="29bfd-150">Cuando se incluye el parámetro detallado, test-CsLocationPolicy devolverá una cuenta paso a paso de cada acción que intentó realizar al comprobar la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="29bfd-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="29bfd-151">Por ejemplo, este resultado indica que Lync Server no pudo iniciar sesión en el usuario de prueba, probablemente porque se proporcionó una contraseña no válida:</span><span class="sxs-lookup"><span data-stu-id="29bfd-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="29bfd-152">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="29bfd-152">Sending Registration request :</span></span>

<span data-ttu-id="29bfd-153">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29bfd-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="29bfd-154">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29bfd-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="29bfd-155">Registrar puerto = 5061</span><span class="sxs-lookup"><span data-stu-id="29bfd-155">Registrar Port = 5061</span></span>

<span data-ttu-id="29bfd-156">El tipo de autenticación ' IWA ' está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="29bfd-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="29bfd-157">Registro de visitas contra SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="29bfd-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29bfd-158">Actividad ' Register ' completada en ' 0,0601795 ' s.</span><span class="sxs-lookup"><span data-stu-id="29bfd-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="29bfd-159">Excepción ' se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="29bfd-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="29bfd-160">Compruebe que se están usando las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="29bfd-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="29bfd-161">durante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="29bfd-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29bfd-162">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="29bfd-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="29bfd-163">Estas son algunas de las razones comunes por las que test-CsLocationPolicy podría fallar:</span><span class="sxs-lookup"><span data-stu-id="29bfd-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="29bfd-164">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="29bfd-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="29bfd-165">Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="29bfd-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="29bfd-166">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29bfd-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="29bfd-167">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="29bfd-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="29bfd-168">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29bfd-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

