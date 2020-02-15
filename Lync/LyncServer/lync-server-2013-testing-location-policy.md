---
title: 'Lync Server 2013: Directiva de ubicación de pruebas'
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
ms.openlocfilehash: 2a46eecb63ed35075cb44ff840e733f781357ea6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="3ae44-102">Directiva de ubicación de pruebas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ae44-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ae44-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3ae44-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ae44-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="3ae44-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3ae44-105">Diario</span><span class="sxs-lookup"><span data-stu-id="3ae44-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ae44-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="3ae44-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3ae44-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ae44-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ae44-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="3ae44-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3ae44-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3ae44-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3ae44-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="3ae44-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="3ae44-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3ae44-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3ae44-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ae44-112">Description</span></span>

<span data-ttu-id="3ae44-113">El cmdlet test-CsLocationPolicy comprueba que una directiva de ubicación está asignada a un usuario.</span><span class="sxs-lookup"><span data-stu-id="3ae44-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="3ae44-114">La Directiva de ubicación se usa para aplicar la configuración relacionada con la funcionalidad de E9-1-1 y la ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="3ae44-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="3ae44-115">La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si la respuesta es "sí", cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="3ae44-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="3ae44-116">Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ae44-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="3ae44-117">Puede probar directivas de ubicación en usuarios o subredes.</span><span class="sxs-lookup"><span data-stu-id="3ae44-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="3ae44-118">Si ejecuta la prueba en una subred (mediante la especificación de un valor para el parámetro Subnet), el cmdlet intentará resolver la directiva de ubicación para esa subred.</span><span class="sxs-lookup"><span data-stu-id="3ae44-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="3ae44-119">Si no se asigna ninguna directiva de ubicación a la subred, se recuperará la directiva de ubicación para el usuario configurado.</span><span class="sxs-lookup"><span data-stu-id="3ae44-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="3ae44-120">Si la Directiva de subred se recupera correctamente, el resultado incluirá un valor de LocationPolicyTagID que empieza con subnet-TagID.</span><span class="sxs-lookup"><span data-stu-id="3ae44-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="3ae44-121">Si no se encontró una directiva de ubicación para la subred, LocationPolicyTagID comenzará con el Id. de etiqueta del usuario.</span><span class="sxs-lookup"><span data-stu-id="3ae44-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3ae44-122">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="3ae44-122">Running the test</span></span>

<span data-ttu-id="3ae44-123">El cmdlet test-CsLocationPolicy se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ae44-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="3ae44-124">Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="3ae44-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="3ae44-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ae44-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3ae44-126">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="3ae44-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="3ae44-127">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="3ae44-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="3ae44-128">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="3ae44-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3ae44-129">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="3ae44-129">Determining success or failure</span></span>

<span data-ttu-id="3ae44-130">Si el usuario especificado tiene una directiva de ubicación válida, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="3ae44-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3ae44-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="3ae44-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="3ae44-132">LocationPolicyTagID: usuario-TagID</span><span class="sxs-lookup"><span data-stu-id="3ae44-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="3ae44-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ae44-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ae44-134">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="3ae44-134">Result : Success</span></span>

<span data-ttu-id="3ae44-135">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="3ae44-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="3ae44-136">Error</span><span class="sxs-lookup"><span data-stu-id="3ae44-136">Error :</span></span>

<span data-ttu-id="3ae44-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3ae44-137">Diagnosis :</span></span>

<span data-ttu-id="3ae44-138">Si no se encuentra una directiva de ubicación válida para el usuario especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="3ae44-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3ae44-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ae44-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ae44-140">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="3ae44-140">Result : Failure</span></span>

<span data-ttu-id="3ae44-141">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3ae44-141">Latency : 00:00:00</span></span>

<span data-ttu-id="3ae44-142">Error: 404, no encontrado</span><span class="sxs-lookup"><span data-stu-id="3ae44-142">Error : 404, Not Found</span></span>

<span data-ttu-id="3ae44-143">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ae44-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="3ae44-144">Razón = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="3ae44-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="3ae44-145">haber.</span><span class="sxs-lookup"><span data-stu-id="3ae44-145">exist.</span></span>

<span data-ttu-id="3ae44-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="3ae44-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3ae44-147">La salida anterior indica que se produjo un error en la prueba porque el usuario especificado no es válido: la cuenta no existe o el usuario no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ae44-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="3ae44-148">Puede comprobar la validez de una cuenta y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ae44-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="3ae44-149">Si test-CsLocationPolicy produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="3ae44-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="3ae44-150">Cuando se incluye el parámetro verbose, test-CsLocationPolicy devolverá una cuenta paso a paso de cada acción que intentó realizar la comprobación de la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="3ae44-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="3ae44-151">Por ejemplo, este resultado indica que Lync Server no pudo iniciar sesión en el usuario de prueba, probablemente debido a que se ha proporcionado una contraseña no válida:</span><span class="sxs-lookup"><span data-stu-id="3ae44-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="3ae44-152">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="3ae44-152">Sending Registration request :</span></span>

<span data-ttu-id="3ae44-153">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ae44-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="3ae44-154">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3ae44-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="3ae44-155">Puerto del registrador = 5061</span><span class="sxs-lookup"><span data-stu-id="3ae44-155">Registrar Port = 5061</span></span>

<span data-ttu-id="3ae44-156">El tipo de autenticación "IWA" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3ae44-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="3ae44-157">Aciertos de registro en SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="3ae44-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3ae44-158">La actividad "Register" se completó en "0,0601795" segundos.</span><span class="sxs-lookup"><span data-stu-id="3ae44-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="3ae44-159">Excepción: "se denegó el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3ae44-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="3ae44-160">Compruebe que se usan las credenciales correctas y que la cuenta está activa.</span><span class="sxs-lookup"><span data-stu-id="3ae44-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="3ae44-161">se produjo durante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ae44-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3ae44-162">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="3ae44-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="3ae44-163">Estas son algunas de las razones comunes por las que test-CsLocationPolicy podría fallar:</span><span class="sxs-lookup"><span data-stu-id="3ae44-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="3ae44-164">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="3ae44-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="3ae44-165">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ae44-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3ae44-166">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ae44-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3ae44-167">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ae44-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="3ae44-168">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ae44-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

