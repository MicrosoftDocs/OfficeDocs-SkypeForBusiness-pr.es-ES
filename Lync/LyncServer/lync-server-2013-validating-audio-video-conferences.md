---
title: 'Lync Server 2013: validación de conferencias de audio y vídeo'
description: 'Lync Server 2013: validación de conferencias de audio y vídeo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad12611e928a64b934252ec21c18b98366e0912b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547206"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="34dd6-103">Validar conferencias de audio y vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34dd6-103">Validating audio/video conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34dd6-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="34dd6-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34dd6-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="34dd6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="34dd6-106">Diario</span><span class="sxs-lookup"><span data-stu-id="34dd6-106">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34dd6-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="34dd6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="34dd6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dd6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34dd6-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="34dd6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="34dd6-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="34dd6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="34dd6-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsAVConference.</span><span class="sxs-lookup"><span data-stu-id="34dd6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="34dd6-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="34dd6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="34dd6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="34dd6-113">Description</span></span>

<span data-ttu-id="34dd6-114">El cmdlet Test-CsAVConference comprueba si dos usuarios de prueba pueden participar en una conferencia de audio y vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="34dd6-114">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="34dd6-115">Cuando se ejecuta el cmdlet, los dos usuarios ya deben haber iniciado sesión en el sistema.</span><span class="sxs-lookup"><span data-stu-id="34dd6-115">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="34dd6-116">Una vez que se han conectado correctamente, el primer usuario crea una conferencia A/V y, a continuación, espera a que el segundo usuario se una a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="34dd6-116">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="34dd6-117">Después de un breve intercambio de datos, la conferencia se elimina y los dos usuarios de prueba finalizan la sesión.</span><span class="sxs-lookup"><span data-stu-id="34dd6-117">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="34dd6-118">Tenga en cuenta que Test-CsAVConference no lleva A cabo una conferencia A/V real entre los dos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="34dd6-118">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="34dd6-119">En su lugar, el cmdlet comprueba que los dos usuarios pueden realizar todas las conexiones necesarias para llevar a cabo una conferencia de este tipo.</span><span class="sxs-lookup"><span data-stu-id="34dd6-119">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="34dd6-120">Puede encontrar más ejemplos para este comando en [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="34dd6-120">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="34dd6-121">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="34dd6-121">Running the test</span></span>

<span data-ttu-id="34dd6-122">El cmdlet Test-CsAVConference puede ejecutarse con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34dd6-122">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="34dd6-123">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="34dd6-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="34dd6-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="34dd6-124">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="34dd6-125">Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="34dd6-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="34dd6-126">A continuación, debe incluir los objetos de credenciales y las direcciones SIP de las dos cuentas cuando llaman a test-CsAVConference:</span><span class="sxs-lookup"><span data-stu-id="34dd6-126">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="34dd6-127">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="34dd6-127">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="34dd6-128">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="34dd6-128">Determining Success or Failure</span></span>

<span data-ttu-id="34dd6-129">Si los usuarios especificados pueden completar correctamente una conferencia A/V, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="34dd6-129">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="34dd6-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="34dd6-131">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="34dd6-131">Result : Success</span></span>

<span data-ttu-id="34dd6-132">Latencia: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="34dd6-132">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="34dd6-133">Error</span><span class="sxs-lookup"><span data-stu-id="34dd6-133">Error :</span></span>

<span data-ttu-id="34dd6-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="34dd6-134">Diagnosis :</span></span>

<span data-ttu-id="34dd6-135">Si los usuarios no pueden completar la Conferencia, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="34dd6-135">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="34dd6-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="34dd6-137">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="34dd6-137">Result : Failure</span></span>

<span data-ttu-id="34dd6-138">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="34dd6-138">Latency : 00:00:00</span></span>

<span data-ttu-id="34dd6-139">Error: 404, no encontrado</span><span class="sxs-lookup"><span data-stu-id="34dd6-139">Error : 404, Not Found</span></span>

<span data-ttu-id="34dd6-140">Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-140">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="34dd6-141">Razón = URI de destino no habilitado para SIP o no</span><span class="sxs-lookup"><span data-stu-id="34dd6-141">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="34dd6-142">haber.</span><span class="sxs-lookup"><span data-stu-id="34dd6-142">exist.</span></span>

<span data-ttu-id="34dd6-143">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="34dd6-143">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="34dd6-144">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque al menos una de las dos cuentas de usuario no era válida, ya sea porque la cuenta no existe o porque la cuenta no se ha habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34dd6-144">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="34dd6-145">Puede comprobar la existencia de las dos cuentas de prueba y si se habilitaron para Lync Server, mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="34dd6-145">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="34dd6-146">Si Test-CsAVConference da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="34dd6-146">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="34dd6-147">Cuando se incluye el parámetro verbose, Test-CsAVConference devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad de los usuarios especificados para participar en una conferencia antivirus.</span><span class="sxs-lookup"><span data-stu-id="34dd6-147">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="34dd6-148">Por ejemplo, supongamos que la prueba produce un error y recibe el siguiente diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="34dd6-148">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="34dd6-149">ErrorCode = 1008, Source = accessproxy. litwareinc. com, causa = no se puede resolver el registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="34dd6-149">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="34dd6-150">Si vuelve a ejecutar la prueba mediante el parámetro verbose, la información devuelta incluirá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="34dd6-150">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="34dd6-151">VERBOse: Activity "Register" (registro) iniciada.</span><span class="sxs-lookup"><span data-stu-id="34dd6-151">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="34dd6-152">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="34dd6-152">Sending Registration request:</span></span>

<span data-ttu-id="34dd6-153">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-153">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="34dd6-154">Dirección SIP del usuario = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-154">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="34dd6-155">Puerto del registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="34dd6-155">Registrar Port = 5061.</span></span>

<span data-ttu-id="34dd6-156">El tipo de autenticación "de confianza" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="34dd6-156">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="34dd6-157">Actividad de "registro" iniciada.</span><span class="sxs-lookup"><span data-stu-id="34dd6-157">'Register' activity started.</span></span>

<span data-ttu-id="34dd6-158">Enviando solicitud de registro:</span><span class="sxs-lookup"><span data-stu-id="34dd6-158">Sending Registration request:</span></span>

<span data-ttu-id="34dd6-159">FQDN de destino = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-159">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="34dd6-160">Dirección SIP del usuario = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="34dd6-160">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="34dd6-161">Puerto del registrador = 5061.</span><span class="sxs-lookup"><span data-stu-id="34dd6-161">Registrar Port = 5061.</span></span>

<span data-ttu-id="34dd6-162">El tipo de autenticación "de confianza" está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="34dd6-162">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="34dd6-163">Una excepción ' el punto de conexión no se pudo registrar.</span><span class="sxs-lookup"><span data-stu-id="34dd6-163">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="34dd6-164">Consulte ErrorCode por motivos específicos. '</span><span class="sxs-lookup"><span data-stu-id="34dd6-164">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="34dd6-165">se produjeron durante el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="34dd6-165">occurred during Workflow</span></span>

<span data-ttu-id="34dd6-166">La última línea del resultado indica que el usuario sip:kenmyer@litwareinc.com no pudo registrarse en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34dd6-166">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="34dd6-167">Esto significa que debe comprobar que la dirección SIP sip:kenmyer@litwareinc.com es válida y que el usuario asociado está habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34dd6-167">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="34dd6-168">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="34dd6-168">Reasons why the test might have failed</span></span>

<span data-ttu-id="34dd6-169">Estas son algunas de las razones comunes por las que Test-CsAVConference podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="34dd6-169">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="34dd6-170">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="34dd6-170">You specified a user account that is not valid.</span></span> <span data-ttu-id="34dd6-171">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="34dd6-171">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="34dd6-172">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34dd6-172">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="34dd6-173">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="34dd6-173">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="34dd6-174">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34dd6-174">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

