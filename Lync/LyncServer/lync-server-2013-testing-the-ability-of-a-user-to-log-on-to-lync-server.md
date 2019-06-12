---
title: 'Lync Server 2013: probar la capacidad de un usuario para iniciar sesión en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="c09a4-102">Probar la capacidad de un usuario para iniciar sesión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c09a4-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c09a4-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c09a4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c09a4-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="c09a4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c09a4-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="c09a4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c09a4-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="c09a4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c09a4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c09a4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c09a4-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c09a4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c09a4-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c09a4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c09a4-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="c09a4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="c09a4-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c09a4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c09a4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c09a4-112">Description</span></span>

<span data-ttu-id="c09a4-113">El cmdlet test-CsRegistration le permite comprobar que los usuarios de su organización pueden iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c09a4-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="c09a4-114">Al ejecutar test-CsRegistration, el cmdlet intenta iniciar sesión en Lync Server en un usuario de prueba y, a continuación, si se realiza correctamente, desconecta ese usuario de prueba del sistema.</span><span class="sxs-lookup"><span data-stu-id="c09a4-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="c09a4-115">Todo esto sucede sin ninguna interacción por el usuario y sin afectar a ningún usuario real.</span><span class="sxs-lookup"><span data-stu-id="c09a4-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="c09a4-116">Por ejemplo, supongamos que el sip:kenmyer@litwareinc.com de la cuenta de prueba corresponde a un usuario real que tiene una cuenta real de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c09a4-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="c09a4-117">En ese caso, la prueba se realizará sin interrupciones en real Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c09a4-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="c09a4-118">Cuando la cuenta de prueba Ken Myer cierra la sesión en el sistema, Ken Myer permanecerá en la sesión.</span><span class="sxs-lookup"><span data-stu-id="c09a4-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c09a4-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="c09a4-119">Running the test</span></span>

<span data-ttu-id="c09a4-120">El cmdlet test-CsRegistration se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c09a4-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="c09a4-121">Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de registradores de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="c09a4-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="c09a4-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c09a4-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c09a4-123">Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c09a4-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="c09a4-124">Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsRegistration:</span><span class="sxs-lookup"><span data-stu-id="c09a4-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="c09a4-125">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="c09a4-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c09a4-126">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="c09a4-126">Determining success or failure</span></span>

<span data-ttu-id="c09a4-127">Si el usuario especificado puede iniciar sesión en y, a continuación, cerrar sesión en Lync Server, recibirá una salida similar a la siguiente con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="c09a4-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c09a4-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c09a4-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c09a4-129">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="c09a4-129">Result : Success</span></span>

<span data-ttu-id="c09a4-130">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="c09a4-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="c09a4-131">:</span><span class="sxs-lookup"><span data-stu-id="c09a4-131">Error :</span></span>

<span data-ttu-id="c09a4-132">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c09a4-132">Diagnosis :</span></span>

<span data-ttu-id="c09a4-133">Si el usuario especificado no puede iniciar sesión ni cerrar la sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="c09a4-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c09a4-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c09a4-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c09a4-135">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="c09a4-135">Result : Failure</span></span>

<span data-ttu-id="c09a4-136">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c09a4-136">Latency : 00:00:00</span></span>

<span data-ttu-id="c09a4-137">Error: 404, no se encontró</span><span class="sxs-lookup"><span data-stu-id="c09a4-137">Error : 404, Not Found</span></span>

<span data-ttu-id="c09a4-138">Diagnosis: ErrorCode = 1003, Source = ATL-CS-001. litwareinc. com, razón = el usuario sí</span><span class="sxs-lookup"><span data-stu-id="c09a4-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="c09a4-139">no existe</span><span class="sxs-lookup"><span data-stu-id="c09a4-139">not exist</span></span>

<span data-ttu-id="c09a4-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="c09a4-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="c09a4-141">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="c09a4-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="c09a4-142">Puede determinar si una dirección SIP es válida (y si el usuario asignado a esa dirección SIP está habilitado para Lync Server) ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="c09a4-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="c09a4-143">Si prueba-CsRegistration da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="c09a4-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="c09a4-144">Cuando se incluye el parámetro detallado, test-CsRegistration devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c09a4-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="c09a4-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c09a4-145">For example:</span></span>

<span data-ttu-id="c09a4-146">VERBOse: actividad ' Register ' iniciada.</span><span class="sxs-lookup"><span data-stu-id="c09a4-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="c09a4-147">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="c09a4-147">Sending Registration request:</span></span>

<span data-ttu-id="c09a4-148">FQDN de destino = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c09a4-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="c09a4-149">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c09a4-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="c09a4-150">Registrar puerto = 5061.</span><span class="sxs-lookup"><span data-stu-id="c09a4-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="c09a4-151">El tipo de autenticación "de confianza" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c09a4-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="c09a4-152">Excepción ' el punto de conexión no se puede registrar.</span><span class="sxs-lookup"><span data-stu-id="c09a4-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="c09a4-153">Vea el código de error de motivo específico ' durante el flujo de trabajo Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow Execution.</span><span class="sxs-lookup"><span data-stu-id="c09a4-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="c09a4-154">Pila de llamadas de excepción: en Microsoft. RTC. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="c09a4-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c09a4-155">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="c09a4-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="c09a4-156">Estas son algunas de las razones comunes por las que test-CsRegistration podría fallar:</span><span class="sxs-lookup"><span data-stu-id="c09a4-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="c09a4-157">Ha especificado una cuenta de usuario incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c09a4-157">You specified an incorrect user account.</span></span> <span data-ttu-id="c09a4-158">Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="c09a4-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="c09a4-159">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c09a4-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="c09a4-160">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c09a4-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="c09a4-161">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c09a4-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="c09a4-162">Ha especificado un grupo de registradores incorrecto.</span><span class="sxs-lookup"><span data-stu-id="c09a4-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="c09a4-163">Puede devolver los FQDN de sus grupos de registradores con este comando:</span><span class="sxs-lookup"><span data-stu-id="c09a4-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="c09a4-164">El grupo de registradores no está disponible en este momento.</span><span class="sxs-lookup"><span data-stu-id="c09a4-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="c09a4-165">Intente hacer ping al grupo para ver si responde:</span><span class="sxs-lookup"><span data-stu-id="c09a4-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

