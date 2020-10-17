---
title: 'Lync Server 2013: Directiva de ubicación de pruebas'
description: 'Lync Server 2013: Directiva de ubicación de prueba.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4efc7ac6f3beef875ce1496b19b875ff252b145b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560606"
---
# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="69e1c-103">Directiva de ubicación de pruebas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e1c-103">Testing location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69e1c-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="69e1c-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69e1c-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="69e1c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="69e1c-106">Diario</span><span class="sxs-lookup"><span data-stu-id="69e1c-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e1c-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="69e1c-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="69e1c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69e1c-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69e1c-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="69e1c-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="69e1c-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="69e1c-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="69e1c-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="69e1c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="69e1c-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="69e1c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="69e1c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="69e1c-113">Description</span></span>

<span data-ttu-id="69e1c-114">El cmdlet Test-CsLocationPolicy comprueba que una directiva de ubicación está asignada a un usuario.</span><span class="sxs-lookup"><span data-stu-id="69e1c-114">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="69e1c-115">La Directiva de ubicación se usa para aplicar la configuración relacionada con la funcionalidad de E9-1-1 y la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="69e1c-115">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="69e1c-116">La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si la respuesta es "sí", cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="69e1c-116">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="69e1c-117">Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="69e1c-117">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="69e1c-118">Puede probar directivas de ubicación en usuarios o subredes.</span><span class="sxs-lookup"><span data-stu-id="69e1c-118">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="69e1c-119">Si ejecuta la prueba en una subred (mediante la especificación de un valor para el parámetro Subnet), el cmdlet intentará resolver la directiva de ubicación para esa subred.</span><span class="sxs-lookup"><span data-stu-id="69e1c-119">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="69e1c-120">Si no se asigna ninguna directiva de ubicación a la subred, se recuperará la directiva de ubicación para el usuario configurado.</span><span class="sxs-lookup"><span data-stu-id="69e1c-120">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="69e1c-121">Si la Directiva de subred se recupera correctamente, el resultado incluirá un valor de LocationPolicyTagID que empieza con subnet-TagID.</span><span class="sxs-lookup"><span data-stu-id="69e1c-121">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="69e1c-122">Si no se encontró una directiva de ubicación para la subred, LocationPolicyTagID comenzará con el Id. de etiqueta del usuario.</span><span class="sxs-lookup"><span data-stu-id="69e1c-122">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="69e1c-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="69e1c-123">Running the test</span></span>

<span data-ttu-id="69e1c-124">El cmdlet Test-CsLocationPolicy se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69e1c-124">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="69e1c-125">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="69e1c-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="69e1c-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="69e1c-126">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="69e1c-127">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="69e1c-127">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="69e1c-128">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="69e1c-128">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="69e1c-129">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="69e1c-129">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="69e1c-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="69e1c-130">Determining success or failure</span></span>

<span data-ttu-id="69e1c-131">Si el usuario especificado tiene una directiva de ubicación válida, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="69e1c-131">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="69e1c-132">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="69e1c-132">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="69e1c-133">LocationPolicyTagID: usuario-TagID</span><span class="sxs-lookup"><span data-stu-id="69e1c-133">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="69e1c-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69e1c-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69e1c-135">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="69e1c-135">Result : Success</span></span>

<span data-ttu-id="69e1c-136">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="69e1c-136">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="69e1c-137">Error</span><span class="sxs-lookup"><span data-stu-id="69e1c-137">Error :</span></span>

<span data-ttu-id="69e1c-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="69e1c-138">Diagnosis :</span></span>

<span data-ttu-id="69e1c-139">Si no se encuentra una directiva de ubicación válida para el usuario especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="69e1c-139">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="69e1c-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69e1c-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69e1c-141">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="69e1c-141">Result : Failure</span></span>

<span data-ttu-id="69e1c-142">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69e1c-142">Latency : 00:00:00</span></span>

<span data-ttu-id="69e1c-143">Error: 404, no encontrado</span><span class="sxs-lookup"><span data-stu-id="69e1c-143">Error : 404, Not Found</span></span>

<span data-ttu-id="69e1c-144">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69e1c-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="69e1c-145">Razón = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="69e1c-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="69e1c-146">haber.</span><span class="sxs-lookup"><span data-stu-id="69e1c-146">exist.</span></span>

<span data-ttu-id="69e1c-147">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="69e1c-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="69e1c-148">La salida anterior indica que se produjo un error en la prueba porque el usuario especificado no es válido: la cuenta no existe o el usuario no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69e1c-148">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="69e1c-149">Puede comprobar la validez de una cuenta y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="69e1c-149">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="69e1c-150">Si Test-CsLocationPolicy da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="69e1c-150">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="69e1c-151">Cuando se incluye el parámetro verbose, Test-CsLocationPolicy devolverá una cuenta paso a paso de cada acción que intentó realizar al comprobar la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="69e1c-151">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="69e1c-152">Por ejemplo, este resultado indica que Lync Server no pudo iniciar sesión en el usuario de prueba, probablemente debido a que se ha proporcionado una contraseña no válida:</span><span class="sxs-lookup"><span data-stu-id="69e1c-152">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="69e1c-153">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="69e1c-153">Sending Registration request :</span></span>

<span data-ttu-id="69e1c-154">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69e1c-154">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="69e1c-155">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69e1c-155">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="69e1c-156">Puerto del registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="69e1c-156">Registrar Port = 5061</span></span>

<span data-ttu-id="69e1c-157">El tipo de autenticación "IWA" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69e1c-157">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="69e1c-158">Aciertos de registro en SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="69e1c-158">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69e1c-159">La actividad "Register" se completó en "0,0601795" segundos.</span><span class="sxs-lookup"><span data-stu-id="69e1c-159">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="69e1c-160">Excepción: "se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="69e1c-160">An exception 'The log on was denied.</span></span> <span data-ttu-id="69e1c-161">Compruebe que se usan las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="69e1c-161">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="69e1c-162">se produjo durante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69e1c-162">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="69e1c-163">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="69e1c-163">Reasons why the test might have failed</span></span>

<span data-ttu-id="69e1c-164">Estas son algunas de las razones comunes por las que Test-CsLocationPolicy podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="69e1c-164">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="69e1c-165">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="69e1c-165">You specified a user account that is not valid.</span></span> <span data-ttu-id="69e1c-166">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="69e1c-166">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="69e1c-167">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69e1c-167">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="69e1c-168">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="69e1c-168">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="69e1c-169">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69e1c-169">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

